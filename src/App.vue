<template>
  <div class="app activ">
    <div class="todo-container">
      <header class="header">
        <h1>TODO</h1>
        <img src="./assets/ICON-MOON.SVG" />
      </header>
      <main>
        <ToDoInput :addTodo="addTodo" v-model="newToDo" />
        <TodoList
          :toDos="toDos"
          :removeToDo="removeToDo"
          :editToDo="editToDo"
          :editedToDo="editedToDo"
          v-model="editedToDoText"
          :updateToDo="updateToDo"
          :toggleCompletion="toggleCompletion"
        />
      </main>
    </div>
    <div class="drag">
      <p>Drag and drop to reorder list</p>
    </div>
  </div>
</template>
<script>
import ToDoInput from "./components/TodoInput/TodoInput.vue";
import TodoList from "./components/TodoList/TodoList.vue";

export default {
  name: "App",
  components: {
    ToDoInput,
    TodoList,
  },
  data() {
    return {
      toDos: [],
      newToDo: " ",
      toDoID: 0,
      editedToDo: null,
      editedToDoText: "",
    };
  },
  methods: {
    addTodo() {
      if (this.newToDo.trim().length == 0) {
        return;
      }
      this.toDos.push({
        id: this.toDoID,
        text: this.newToDo,
        todoCompletionButtonState: "",
        todoCompletionState: "incomplete",
      });
      this.toDoID++;
      this.newToDo = "";
    },
    removeToDo(todo) {
      this.toDos.splice(this.toDos.indexOf(todo), 1);
    },
    editToDo(todo) {
      this.editedToDo = todo;
      this.editedToDoText = todo.text;
      this.editedToDoText = todo.text;
    },
    updateToDo(todo) {
      if (!this.editedToDo) {
        return;
      } else if (!todo.text) {
        this.removeToDo(todo);
      }
      this.editedToDo = null;
      todo.text = this.editedToDoText.trim();
    },
    toggleCompletion(todo) {
      if (
        todo.todoCompletionButtonState === " " ||
        todo.todoCompletionButtonState === false
      ) {
        todo.todoCompletionButtonState = "checked";
        todo.todoCompletionState = "completed";
      } else if (
        todo.todoCompletionButtonState === "checked" ||
        todo.todoCompletionButtonState === true
      ) {
        todo.todoCompletionButtonState = "";
        todo.todoCompletionState = "incomplete";
      }
    },
  },
};
</script>
<style lang="scss">
@import "./App.scss";
</style>
