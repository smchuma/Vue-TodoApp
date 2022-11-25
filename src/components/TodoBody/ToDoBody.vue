<script setup>
import ToDoList from "../ToDoList/ToDoList.vue";
</script>
<template>
  <div class="container">
    <ul class="todo-list">
      <ToDoList />
      <ToDoList />
      <ToDoList />
      <ToDoList />
    </ul>
    ssss
  </div>
</template>

<style lang="scss" scoped>
.container {
  background: rgb(255, 255, 255);
  margin-top: 25px;
  border: 1px solid hsl(233, 11%, 84%);

  border-radius: 5px;
  .todo-list {
    /* margin-left: 20px; */
  }
}
</style>
