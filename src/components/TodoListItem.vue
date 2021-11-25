<template>
  <div id="todo-list-item">
    <div>
      <input type="checkbox" v-model="checked" />
    </div>
    <div>
      <span :class="removed">{{ todoText }}</span>
    </div>
    <div>
      <button @click="onRemove">삭제</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoListItem",
  props: {
    todoText: { type: String, required: true },
    id: { type: Number, required: true },
  },
  data() {
    return {
      checked: false,
    };
  },
  methods: {
    onRemove: function() {
      this.$emit("remove", this.id);
    },
  },
  computed: {
    removed: function() {
      return this.checked === true ? "removed" : "";
    },
  },
};
</script>

<style>
#todo-list-item {
  padding: 20px;
  display: flex;
  align-items: center;
}

#todo-list-item div:nth-child(2) {
  flex: 2;
  margin-left: 10px;
}

#todo-list-item div:nth-child(3) button {
  background: red;
  color: white;
  border: none;
  outline: none;
  border-radius: 5px;
  height: 25px;
  cursor: pointer;
}

#todo-list-item:nth-child(even) {
  background: #f8f9fa;
}

#todo-list-item .removed {
  text-decoration: line-through;
}
</style>
