<template>
  <h1>{{ msg }}</h1>
  <Comp></Comp>
  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">Vite Documentation</a> |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button @click="state.count++">count is: {{ state.count }}</button>
  <button @click="emit('myclick')">emit</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
// 1.直接导入组件
import Comp from 'comps/Comp.vue'
import { defineProps, reactive, defineEmit, useContext } from 'vue'

// 2.属性定义
defineProps({
  msg: String
})

// 3.获取上下文
const ctx = useContext()
console.log(ctx);


ctx.expose({
  someMethod() {
    console.log('some message from helloword');
  }
})

// 4.定义事件
const emit = defineEmit(['myclick'])

const onClick = () =>{
  ctx.emit('myclick')
}
const state = reactive({ count: 0 })


</script>

<style scoped>
a {
  color: #42b983;
}
</style>