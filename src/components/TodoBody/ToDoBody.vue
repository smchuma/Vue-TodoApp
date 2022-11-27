<template>
  <div class="container">
    <ul class="todo-list">
      <ToDoList :toDos="toDos" :removeToDo="removeToDo" />
    </ul>
    <ToDoFooter />
  </div>
</template>

<script>
import ToDoList from "../ToDoList/ToDoList.vue";
import ToDoFooter from "../ToDoFooter/ToDoFooter.vue";
export default {
  name: "ToDoBody",
  components: {
    ToDoList,
    ToDoFooter,
  },
  props: {
    toDos: {
      type: Array,
      required: true,
    },
    removeToDo: {
      type: Function,
      required: true,
    },
  },
};
</script>
<style lang="scss">
.container {
  background: white;
  margin-top: 30px;
  width: 100%;
  border-radius: 5px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.1);

  .todo-list {
    list-style: none;
  }
}
</style>
