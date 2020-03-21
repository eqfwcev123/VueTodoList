<template>
  <div class="inputBox shadow">
    <!-- input에 입력한 텍스트 값을 동적으로 뷰 인스턴스로 매핑한다 -->
    <!-- v-on:keyup.enter 은 enter키가 눌렸을때 addTodo함수를 호출하는 것이다.-->
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">

    <!-- <button v-on:click="addTodo">add</button> -->
    <!-- button태그 대신에 fontawesome 아이콘에 button의 기능을 추가 -->
    <span class="addContainer" v-on:click="addTodo">
      <i class="fas fa-plus addBtn"></i>
    </span>

  </div>
</template>

<script>
// 이쪽 영역을 Vue인스턴스의 영역이라고 보면된다
// 즉 this는 아래에 있는 TodoInput 컴포넌트를 의미한다
export default {
  data() {
    return {
      newTodoItem: ""
    }
  },
  methods: {
    addTodo() {
      // 저장하는 로직
      localStorage.setItem(this.newTodoItem, this.newTodoItem);
      this.clearInput();
    },
    clearInput(){
      this.newTodoItem="";
    }
  },
}
</script>

<style scoped>
.inputBox{
  background:white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}

.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}

.addContainer{
  float: right;
  background: linear-gradient(to right, #6478FB, #8763FB);
  display: block; 
  width: 3rem;
  border-radius: 0 5px 5px 0;
}

.addBtn{
  color: white;
  vertical-align: middle;
}
</style>