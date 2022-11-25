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
    <div class="todo-buttons">
      <div class="item-number">
        <p>2 items left</p>
      </div>
      <div class="btn">
        <div class="all">All</div>
        <div class="active">Active</div>
        <div class="completed">Completed</div>
      </div>
      <div class="clear">
        <div class="clear-completed">Clear Completed</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  background: rgb(255, 255, 255);
  margin-top: 25px;
  border: 1px solid hsl(233, 11%, 84%);
  border-radius: 5px;

  .todo-buttons {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;

    .item-number {
      p {
        font-size: 14px;
        color: hsl(236, 9%, 61%);
        font-weight: 400;
      }
    }
    .btn {
      display: flex;

      div {
        margin: 0 10px;
        font-size: 15px;
        color: hsl(236, 9%, 61%);
        font-weight: 400;
        cursor: pointer;
      }
      .all {
        color: hsl(220, 98%, 61%);
      }
    }
    .clear {
      div {
        font-size: 15px;
        color: hsl(236, 9%, 61%);
        font-weight: 400;
        cursor: pointer;
      }
    }
  }
}
</style>
