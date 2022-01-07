<template>
  <div>Count : {{ nilai }}</div>
  <button @click="add">Add</button>
  <div>Result : {{ result }}</div>
</template>

<script>
import { ref, reactive, toRefs, computed } from "vue";
export default {
  
  setup() {
    const counter = reactive({
      nilai: 0,
    });

    const addNum = ref(1);

    const add = () => {
      counter.nilai++;
    };

    const result = computed(() => {
      return counter.nilai + addNum.value;
    });

    return {
      ...toRefs(counter),
      add,
      result
    };
  },

};
</script>
