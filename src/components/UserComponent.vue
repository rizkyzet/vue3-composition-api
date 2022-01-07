<template>
  <div>{{ label }} : {{ user.name }}</div>
  <div>{{ description }}</div>

  <button @click="submit">Submit</button>
  <hr />
  <slot></slot>
</template>

<script>
import { ref, toRefs, computed, onMounted } from "vue";
export default {
    // agar tidakk ada warning extraneous
  inheritAttrs: false,
  props: {
    label: {
      type: String,
      default: "",
    },
    user: {
      type: Object,
      default: {},
    },
  },
  // setup(props,context)
  setup(props, { attrs, slots, emit }) {
    const { label, user } = toRefs(props);
    const description = computed(() => {
      return `${label.value} : ${user.value.name}`;
    });

    onMounted(() => {
      //   console.log(attrs);
      //   console.log(slots);
    });

    const submit = () => {
      emit("submit", "ini adalah emit dari user component");
    };

    return { description, submit };
  },
};
</script>
