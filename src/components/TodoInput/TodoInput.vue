<template>
  <div>
    <div class="heading activ">
      <div class="input">
        <img src="../../assets/FAVICON-32X32.PNG" alt="" />
        <input
          type="text"
          placeholder="Create a new todo"
          autofocus
          :value="modelValue"
          @keyup.enter="addTodo"
          @input="$emit('update:modelValue', $event.target.value)"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "TodoInput",
  props: ["addTodo", "modelValue"],
};
</script>
<style lang="scss">
@import "./TodoInput.scss";
</style>
