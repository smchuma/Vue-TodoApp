<template>
  <div class="todo-footer">
    <span class="count"> {{ itemLeft }} items left </span>
    <ul class="btn">
      <li class="active">
        <a href="#" class="all-btn">All</a>
      </li>
      <li>
        <a href="#" class="active-btn" @click="showActive">Active</a>
      </li>
      <li>
        <a href="#" class="completed-btn" @click="showCompleted">Completed</a>
      </li>
    </ul>
    <button class="clear-btn" @click="clearCompleted">Clear Completed</button>
  </div>
</template>
<script>
export default {
  name: "ToDoFooter",
  props: ["clearCompleted", "itemLeft", "showActive", "showCompleted"],
};
</script>
<style lang="scss">
@import "./ToDoFooter.scss";
</style>
