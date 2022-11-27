<template>
  <div class="app activ">
    <div class="todo-container">
      <header class="header">
        <h1>TODO</h1>
        <img src="./assets/ICON-MOON.SVG" />
      </header>
      <main>
        <ToDoInput :addTodo="addTodo" v-model="newToDo" />
        <ToDoBody
          :toDos="toDos"
          :removeToDo="removeToDo"
          :editToDo="editToDo"
          :editedToDo="editedToDo"
          v-model="editedToDoText"
          :updateToDo="updateToDo"
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
import ToDoBody from "./components/TodoBody/ToDoBody.vue";

export default {
  name: "App",
  components: {
    ToDoInput,
    ToDoBody,
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
        completionButtonState: "",
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
  },
};
</script>
<style lang="scss">
@import "./App.scss";
</style>
