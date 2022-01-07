<template>
  <div>Count : {{ nilai }}</div>
  <button @click="add">Add</button>
</template>

<script>
import { ref, reactive, toRefs, watch, watchEffect, computed } from "vue";
export default {
  setup() {
    const counter = reactive({
      nilai: 0,
      foo: "bar",
    });

    const num1 = ref(1);
    const num2 = ref(2);

    const add = () => {
      // counter.nilai++;
      num1.value++;
      num2.value++;
    };

    // WATCH MANY DATA
    watch([num1, num2], (after, before) => {
      console.log(num1.value);
      console.log(num2.value);
      console.log(after);
      console.log(before);
    });

    // // WATCH SINGLE DATA / NORMAL DATA
    // watch(num1, (after, before) => {
    //   console.log(num1.value);
    //   console.log(after);
    //   console.log(before);
    // });

    // // WATCH OBJECT
    // watch(
    //   () => {
    //     return counter.nilai;
    //   },
    //   (current, before) => {
    //     console.log(counter.nilai);
    //     console.log(current);
    //     console.log(before);
    //   }
    // );

    return {
      ...toRefs(counter),
      add,
    };
  },
};
</script>
