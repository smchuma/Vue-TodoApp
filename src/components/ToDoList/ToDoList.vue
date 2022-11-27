<template>
  <li class="list" v-for:="toDo in toDos">
    <div class="view" key="toDo.id">
      <input type="checkbox" class="toggle" />
      <label>{{ toDo.text }}</label>
      <button class="remove">
        <img
          src="../../assets/ICON-CROSS.SVG"
          alt="cross"
          v-on:click="removeToDo(toDo)"
        />
      </button>
    </div>
    <input class="edit" value="edit a todo" />
  </li>
</template>

<script>
export default {
  name: "ToDoList",
  props: ["toDos", "removeToDo"],
};
</script>

<style lang="scss">
@import "./ToDoList.scss";
</style>
