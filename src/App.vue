<template>
  <img alt='Vue logo' src='./assets/logo.png'>
  <HelloWorld msg='Welcome to Your Vue.js + TypeScript App'/>
  <Couter />
  <Teste msg="Esta é uma propriedade vue"/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld from './components/HelloWorld.vue';
import Couter from './components/Couter.vue';
import Teste from './components/Teste.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
    Couter,
    Teste,
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
