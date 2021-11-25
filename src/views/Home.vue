<template>
  <div class="home">
    <TodoTemplate />
  </div>
</template>

<script>
// @ is an alias to /src
import TodoTemplate from "@/components/TodoTemplate.vue";

export default {
  name: "Home",
  components: {
    TodoTemplate,
  },
};
</script>
