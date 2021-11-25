<template>
  <div id="todo-template">
    <header>
      <h1>일정 관리</h1>
    </header>
    <TodoInsert v-on:insert="insertTodoItem" />
    <TodoList :todos="todos" v-on:remove="removeTodoItem" />
  </div>
</template>

<script>
import TodoInsert from "./TodoInsert.vue";
import TodoList from "./TodoList.vue";

export default {
  name: "TodoTemplate",
  data() {
    return {
      id: 1,
      todos: [],
    };
  },
  methods: {
    insertTodoItem: function(todoText) {
      alert("할 일이 추가되었습니다.");
      this.todos = this.todos.concat({ id: this.id++, todoText });
    },
    removeTodoItem: function(removedId) {
      this.todos = this.todos.filter((todo) => todo.id !== removedId);
    },
  },
  components: {
    TodoInsert,
    TodoList,
  },
};
</script>
<style>
#todo-template {
  width: 40%;
}

#todo-template header {
  background: skyblue;
  color: #ffffff;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

#todo-template header h1 {
  font-weight: 300;
}
</style>
