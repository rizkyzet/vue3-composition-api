<template>
  <div>Count : {{ nilai }}</div>
  <button @click="add">Add</button>
</template>

<script>
import { ref, reactive, toRefs } from "vue";
export default {
  setup() {
    // const counter = ref(0);
    const counter = reactive({
      nilai: 0,
    });

    const add = () => {
      counter.nilai++;
    };

    return {
      ...toRefs(counter),
      add,
    };
  },
};
</script>
