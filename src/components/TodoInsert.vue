<template>
  <div id="todo-insert">
    <input v-model="todoText" type="text" placeholder="할 일을 입력하세요" />
    <button @click="insertTodo">+</button>
  </div>
</template>

<script>
export default {
  name: "TodoInsert",
  data() {
    return {
      todoText: "",
    };
  },
  methods: {
    insertTodo: function() {
      this.$emit("insert", this.todoText); // 부모쪽으로 이벤트 트리거
      this.todoText = "";
    },
  },
};
</script>

<style>
#todo-insert {
  display: flex;
}

#todo-insert input {
  flex: 1;
  outline: none;
  border: none;
  background: #495057;
  color: white;
  line-height: 1.5;
  font-size: 1.125rem;
}

#todo-insert button {
  outline: none;
  border: none;
  color: white;
  cursor: pointer;
  background: #868e96;
}
</style>
