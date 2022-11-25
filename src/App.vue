<script setup>
import ToDoInput from "./components/TodoInput/TodoInput.vue";
import ToDoBody from "./components/TodoBody/ToDoBody.vue";
</script>
<template>
  <div class="app activ">
    <div class="todo-container">
      <header class="header">
        <h2>TODO</h2>
        <img src="./assets/ICON-MOON.SVG" />
      </header>
      <div class="main">
        <ToDoInput />
        <ToDoBody />
      </div>
    </div>
    <div class="footer">
      <p>Drag and drop to reorder list</p>
    </div>
  </div>
</template>

<style lang="scss">
@import "./App.scss";

.main {
}
</style>
