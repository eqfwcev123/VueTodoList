<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
// App.vue 는 Main.js에 등록되어 있다.

import TodoHeader from './components/TodoHeader.vue'
import TodoList from './components/TodoList.vue'
import TodoInput from './components/TodoInput.vue'
import TodoFooter from './components/TodoFooter.vue'

export default{
  components:{
    'TodoHeader':TodoHeader,
    'TodoList':TodoList,
    'TodoInput':TodoInput,
    'TodoFooter':TodoFooter,
  }
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

body{
  text-align: center;
  background-color:#F6F6F6;
}

input{
  border-style:groove;
  width:200px;
}

button{
  border-style:groove;
}

.shadow{
  box-shadow: 5px 10px 10px rgba(0,0,0,0.03);
}
</style>
