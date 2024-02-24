<script>
export default {
  data() {
    return {
      count: 0,
      text: "",
      pick: 1,
      items: [{ message: "msg1" }, { message: "msg2" }],
      myText: "",
    };
  },
  methods: {
    increment() {
      this.count++;
    },
  },
  mounted() {
    console.log(`Count is ${this.count}`);
  },
  updated() {
    console.log(`Count is ${this.count}`);
  },
  computed: {
    isCountEven() {
      return (this.isEven = this.count % 2 == 0 ? true : false);
    },
  },
};
</script>

<template>
  <button @click="increment">Count is {{ count }}</button>
  <p v-if="isCountEven">You can only see me if count is even.</p>
  <p v-else>Count is Odd</p>

  <div>
    <p>List rendering1</p>
    <ul>
      <li v-for="({ message }, index) in items" :key="message">
        {{ index }} - {{ message }}
      </li>
    </ul>
  </div>

  <div>
    <p>Inputs</p>
    <p>Text: {{ myText }}</p>
    <input v-model.trim="myText" />
  </div>
  <div>
    <p>{{ `Pick: ${pick}` }}</p>
    <input type="radio" v-model="pick" :value="1" />
    <input type="radio" v-model="pick" :value="2" />
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
