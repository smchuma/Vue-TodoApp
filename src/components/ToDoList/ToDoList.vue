<template>
  <div class="container">
    <ul class="todo-list">
      <li
        :class="[{ editing: todo == editedToDo }, todo.toggleCompletion]"
        v-for:="todo in toDos"
      >
        <div class="view" key="todo.id">
          <input type="checkbox" @click="toggleCompletion(todo)" />
          <label @dblclick="editToDo(todo)">{{ todo.text }}</label>
          <button class="remove">
            <img
              src="../../assets/ICON-CROSS.SVG"
              alt="cross"
              @click="removeToDo(todo)"
            />
          </button>
        </div>
        <input
          class="edit"
          :value="modelValue"
          @input="$emit('update:modelValue', $event.target.value)"
          @keyup.enter="updateToDo(todo)"
        />
      </li>
    </ul>
    <ToDoFooter />
  </div>
</template>

<script>
import ToDoFooter from "../ToDoFooter/ToDoFooter.vue";
export default {
  name: "TodoList",
  components: {
    ToDoFooter,
  },
  props: [
    "toDos",
    "removeToDo",
    "editToDo",
    "editedToDo",
    "modelValue",
    "updateToDo",
    "toggleCompletion",
  ],
};
</script>
<style lang="scss">
@import "./TodoList.scss";
</style>
