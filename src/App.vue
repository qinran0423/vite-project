<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + Vite"  @myclick="onmyClick" ref="hw"/>
</template>

<script setup>
import HelloWorld from 'comps/HelloWorld.vue'
import { ref } from 'vue';

const hw = ref(null)

const onmyClick = () => {
  console.log('click');
  hw.value.someMethod()
}

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