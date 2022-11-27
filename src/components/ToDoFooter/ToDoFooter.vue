<template lang="">
  <div class="todo-footer">
    <span class="count"> 0 items left </span>
    <ul class="btn">
      <li class="active">
        <a href="#" class="all-btn">All</a>
      </li>
      <li>
        <a href="#" class="active-btn">Active</a>
      </li>
      <li>
        <a href="#" class="completed-btn">Completed</a>
      </li>
    </ul>
    <button class="clear-btn">Clear Completed</button>
  </div>
</template>
<script>
export default {
  name: "ToDoFooter",
};
</script>
<style lang="scss">
@import "./ToDoFooter.scss";
</style>
