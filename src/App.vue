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
          :clearCompleted="clearCompleted"
          :itemLeft="itemLeft"
          :showActive="showActive"
          :showCompleted="showCompleted"
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

const STORAGE_KEY = "vue-todo-app-storage";

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
      allBtn: "selected",
      activeBtn: null,
      completedBtn: null,
    };
  },
  created() {
    this.toDos = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
  },
  computed: {
    itemLeft() {
      return this.toDos.filter((todo) => !todo.completed).length;
    },
  },
  methods: {
    addTodo() {
      if (this.newToDo.trim().length == 0) {
        return;
      }
      this.toDos.push({
        id: this.toDoID,
        text: this.newToDo,
        completed: false,
      });
      this.toDoID++;
      this.newToDo = "";

      localStorage.setItem(STORAGE_KEY, JSON.stringify(this.toDos));
    },
    removeToDo(todo) {
      this.toDos.splice(this.toDos.indexOf(todo), 1);
      localStorage.setItem(STORAGE_KEY, JSON.stringify(this.toDos));
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
      localStorage.setItem(STORAGE_KEY, JSON.stringify(this.toDos));
    },
    clearCompleted() {
      this.toDos = this.toDos.filter((todo) => !todo.completed);
      localStorage.setItem(STORAGE_KEY, JSON.stringify(this.toDos));
    },
    showActive() {
      this.toDos = this.toDos.filter((todo) => !todo.completed);
      this.allBtn = null;
      this.activeBtn = "selected";
      this.completedBtn = null;
    },
    showCompleted() {
      this.toDos = this.toDos.filter((todo) => todo.completed);
      this.allBtn = null;
      this.activeBtn = null;
      this.completedBtn = "selected";
    },
  },
};
</script>
<style lang="scss">
@import "./App.scss";
</style>
