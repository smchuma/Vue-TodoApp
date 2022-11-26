<script setup>
import ToDoList from "../ToDoList/ToDoList.vue";
</script>
<template>
  <div class="container">
    <ul class="todo-list">
      <ToDoList />
    </ul>
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
  </div>
</template>

<style lang="scss" scoped>
.container {
  background: white;
  margin-top: 30px;
  width: 100%;
  border-radius: 5px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.1);

  .todo-list {
    list-style: none;
  }

  .todo-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;

    .count {
      font-size: 14px;
      color: hsl(236, 9%, 61%);
    }

    .btn {
      display: flex;
      list-style: none;
      margin: 0;
      padding: 0;

      li {
        margin-right: 10px;
        a {
          text-decoration: none;
          color: hsl(236, 9%, 61%);
          font-size: 14px;
        }
      }
    }

    .clear-btn {
      background: transparent;
      border: none;
      outline: none;
      font-size: 14px;
      color: hsl(236, 9%, 61%);
      cursor: pointer;
    }
  }
}
</style>
