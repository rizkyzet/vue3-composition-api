<template>
 <div>Name : {{name}}</div>
 <div>Age : {{age}}</div>
</template>

<script>
import {reactive} from "vue";
export default {
  setup() {
  
    const user = reactive({
      name:'Rizkyzet',
      age:"25"
    });

    setTimeout(() => {
      user.name = "Dedy";
    }, 2000);

    return {
      ...user,
    };
  },
};
</script>
