<script>
export default {
  props: ["starter"],
  data() {
    return {
      count: this.starter,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
  },
};
</script>

<template>
  <p>Starts at {{ starter }}</p>
  <div style="display: block">
    <button @click="increment">Count is {{ count }}</button>
  </div>
</template>
