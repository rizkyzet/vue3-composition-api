<template>
  <UserComponent
    :label="label"
    :user="user"
    class="active"
    blabla="testing"
    @submit="onSubmit"
  >
    <div>Ini Slot</div>
  </UserComponent>
  <button @click="changeName">Change</button>
</template>

<script>
import { ref, reactive } from "vue";
import UserComponent from "./components/UserComponent.vue";
export default {
  components: {
    UserComponent,
  },
  setup() {
    const label = ref("biodata");
    const user = reactive({
      name: "Mochamad Rizky",
      age: 18,
    });

    const changeName = () => {
      user.name = "Admin si Jawa";
    };

    const onSubmit = (val) => {
      console.log(val);
    };

    return {
      label,
      user,
      changeName,
      onSubmit
    };
  },
};
</script>
