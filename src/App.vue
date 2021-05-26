<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div></div>
    <!-- <input type="text" v-model="message"> -->
    <HelloWorld msg="paras" />
    <div v-if="num == 4">Paras</div>
    <div v-else-if="num == 55">Prince</div>
    <div v-else>Tamanna</div>
    <div v-for="index in names" v-bind:key="index.id">
      {{ index.id }} {{ index.name }}
    </div>
    <button v-on:click="onclicked">click here</button>
    <h1>{{ newData }}</h1>
    <input type="text" v-model="newData">
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  created() {
    this.sayHello("created hello");
    this.num = 55;
  },
  mounted() {
    this.sayHello("mounted hello");
    this.num = 66;
  },
  data() {
    return {
      num: 4,
      names: [
        {
          id: 1,
          name: "paras",
        },
        {
          id: 2,
          name: "tamanna",
        },
        {
          id: 3,
          name: "prince",
        },
      ],
      newData : "Hello",
    };
  },

  methods: {
    sayHello(greetings) {
      console.log(greetings);
      return greetings;
    },
    onclicked() {
      console.log("Paras Bhardwaj");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
