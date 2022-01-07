<template>
  <div>Count : {{ nilai }}</div>
  <button @click="add">Add</button>
</template>

<script>
import { ref, reactive, toRefs, watchEffect, computed } from "vue";
export default {
  setup() {
    const counter = reactive({
      nilai: 0,
      foo: "bar",
    });

    const add = () => {
      counter.nilai++;
    };

    watchEffect(
      () => {
        console.log(counter.nilai);
      },
      {
        onTrigger(e) {
          console.log(e.oldValue);
        },
        onTrack(e){
          console.log(e)
        }
      }
    );

    return {
      ...toRefs(counter),
      add,
    };
  },
};
</script>
