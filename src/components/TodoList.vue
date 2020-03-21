// TodoInput에서 입력한 값들을 TodoList에 가지고와서 화면에 출력
<template>
  <ul>
    <!-- .shadow 는 App.vue에 있기때문에 위에서 아래로 Cascading된것이다.  -->
    <li v-for="(todoItem, index) in todoItems" v-bind:key="todoItem" class="shadow">
        {{todoItem}}
        <span class="removeBtn">
            <i class="fas fa-trash-alt removeBtn" v-on:click="removeTodo(todoItem, index)"></i>
        </span>
    </li>
  </ul>
</template>

<script>
export default {
    // 인스턴스가 생성되지마자 호출되는 Life Cycle Hook
    data() {
        return {
            todoItems: []
        }
    },
    methods: {
        removeTodo(todoItem, index) {
            // 로컬 스토리지와 배열은 다른것이기 때문에 스토리지에서 지워주고 나서 배열에서도 지워줘야한다
            // 인스턴스가 created 될때 모든 리스트를 한번씩 출력 해주기 때문에 그렇다
            localStorage.removeItem(todoItem);
            // 배열의 index번째 요소를 한개 삭제
            this.todoItems.splice(index,1);
        }
    },
    created () {
        if (localStorage.length) {
            for(let i=0; i<localStorage.length; i++){
                this.todoItems.push(localStorage.key(i));
            }
        } else {
            console.log("로컬스토리지가 비어있습니다");
        }
    },
}
</script>

<style scoped>
ul {
    list-style-type: none;
    padding-left:0;
    margin-top: 0;
    margin-left: 0;
    text-align: left;
}

li{
    display: flex;
    min-height: 50px;
    height: 50px;
    line-height: 50px;
    margin: 0.5rem 0;
    padding: 0 0.9rem;
    background: white;
    border-radius: 5px;
}

.removeBtn{
    margin-left: auto;
    color: #de4343;
}
.checkBtn{
    line-height: 45px;
    color: #62acde;
    margin-right: 5px;
}

.checkBtnCompleted{
    color: #63adad;
}

.textCompleted{
    text-decoration: line-through;
    color: #b3adad;
}

</style>
