<template>
  <li :class="{ editing: todo == editedToDo }" v-for:="todo in toDos">
    <div class="view" key="todo.id">
      <input type="checkbox" class="toggle" />
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
</template>

<script>
export default {
  name: "ToDoList",
  props: [
    "toDos",
    "removeToDo",
    "editToDo",
    "editedToDo",
    "modelValue",
    "updateToDo",
  ],
};
</script>

<style lang="scss">
@import "./ToDoList.scss";
</style>
