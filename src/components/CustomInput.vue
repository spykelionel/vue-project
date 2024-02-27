<script>
export default {
  props: ["modelValue"],
  emits: ["update:modelValue"],
  methods: {},
  computed: {
    value: {
      get() {
        return this.modelValue;
      },
      set(value) {
        return $emit("modelValue", value);
      },
    },
  },
};
</script>

<template>
  <input v-model="value" />
</template>
