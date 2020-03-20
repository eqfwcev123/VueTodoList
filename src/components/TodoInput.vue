<template>
  <div>
    <!-- input에 입력한 텍스트 값을 동적으로 뷰 인스턴스로 매핑한다 -->
    <input v-model="newTodoItem" type="text" />
    <button v-on:click="addTodo"></button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ""
    }
  },
  methods: {
    addTodo() {
      
    }
  },
}
</script>

<style>

</style>