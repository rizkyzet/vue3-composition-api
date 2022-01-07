<template>
  <div>{{ message }}</div>
</template>

<script>
import {ref} from "vue";
export default {
  setup() {
    // ref hanya untuk tipe data string int booelan bukan object array
    const message = ref("halo");

    setTimeout(() => {
      message.value = "composition api";
    }, 2000);

    return {
      message,
    };
  },
};
</script>
