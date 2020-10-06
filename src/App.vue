<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  {{ book }}
  {{ year }}
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

interface Book {
  id: number;
  title: string;
}
export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
  },
  setup() {
    const year = ref<number | string>(2020);
    const book: Book = reactive({ id: 1, title: "Vue 3!" });
    return { book, year };
  },
});
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
