<template>
  <div class="app activ">
    <div class="todo-container">
      <header class="header">
        <h1>TODO</h1>
        <img src="./assets/ICON-MOON.SVG" />
      </header>
      <main>
        <!-- <ToDoInput :addTodo="addTodo" newToDo="newToDo" /> -->
        <div class="heading activ">
          <div class="input">
            <img src="./assets/FAVICON-32X32.PNG" alt="" />
            <input
              type="text"
              placeholder="Create a new todo"
              autofocus
              @keyup.enter="addTodo"
              v-model="newToDo"
            />
          </div>
        </div>
        <ToDoBody :toDos="toDos" :removeToDo="removeToDo" />
      </main>
    </div>
    <div class="drag">
      <p>Drag and drop to reorder list</p>
    </div>
  </div>
</template>
<script>
// import ToDoInput from "./components/TodoInput/TodoInput.vue";
import ToDoBody from "./components/TodoBody/ToDoBody.vue";

export default {
  name: "App",
  components: {
    // ToDoInput,
    ToDoBody,
  },
  data() {
    return {
      toDos: [],
      newToDo: " ",
      toDoID: 0,
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
      this.toDos = this.toDos.filter((toDo) => toDo.id !== todo.id);
    },
  },
};
</script>
<style lang="scss">
@import "./App.scss";
</style>

this.content = event.target.value;
