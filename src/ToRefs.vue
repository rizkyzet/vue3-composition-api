<template>
  <div>Name : {{ name }}</div>
  <div>Age : {{ age }}</div>
</template>

<script>
import { reactive, toRefs, ref } from "vue";
export default {
  setup() {
    const user = reactive({
      name: "Rizkyzet",
      age: "25",
    });

    setTimeout(() => {
      user.name = "Dedy";
    }, 2000);

    return {
      ...toRefs(user),
    };
  },
};
</script>
