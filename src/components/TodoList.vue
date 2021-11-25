<template>
  <div id="todo-list">
    <ul>
      <TodoListItem
        v-for="todo in todos"
        :key="todo.id"
        :todoText="todo.todoText"
        :id="todo.id"
        v-on:remove="removeItem"
      />
    </ul>
  </div>
</template>

<script>
import TodoListItem from "./TodoListItem.vue";

export default {
  name: "TodoList",
  data() {
    return {};
  },
  props: {
    todos: Array,
  },
  methods: {
    removeItem: function(removedId) {
      this.$emit("remove", removedId);
    },
  },
  components: {
    TodoListItem,
  },
};
</script>
<style>
#todo-list {
  height: 400px;
  overflow: auto;
  background: white;
}
#todo-list ul {
  margin: 0;
  padding: 0;
}

#todo-list ul {
  margin: 0;
}

#todo-list li {
  padding: 15px;
  text-decoration: none;
}
</style>
