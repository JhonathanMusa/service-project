<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to the first Vue app" />
  {{ book }}
  {{ book2 }}
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
    const book2: Book = reactive({ id: 2, title: "React!" });
    return { book, book2, year };
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
