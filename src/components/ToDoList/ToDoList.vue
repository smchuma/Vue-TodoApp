<script setup></script>
<template>
  <li class="completed">
    <div class="view">
      <input type="checkbox" class="toggle" checked />
      <label>Learning Vue.js</label>
      <!-- <button class="destroy">button</button> -->
    </div>
    <!-- <input class="edit" value="create a todo" /> -->
  </li>
</template>

<style lang="scss">
.view {
  display: flex;
  align-items: center;
  padding: 20px 10px;
  border-bottom: 1px solid hsl(233, 11%, 84%);
  label {
    margin-left: 12px;
    font-size: 19px;
    color: hsl(235, 19%, 35%);
    font-weight: 400;
  }
  input[type="checkbox"] {
    appearance: none;
    -webkit-appearance: none;
    height: 30px;
    width: 30px;
    background-color: transparent;
    border-radius: 50%;
    border: 1px solid hsl(236, 33%, 92%);
    cursor: pointer;
    outline: none;
  }

  input[type="checkbox"]::after {
    content: url("../../assets/ICON-CHECK.SVG");
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    display: none;
  }
  input[type="checkbox"]:checked {
    background: linear-gradient(
      135deg,
      hsl(192, 100%, 67%) 0%,
      hsl(280, 87%, 65%) 100%
    );
  }

  input[type="checkbox"]:checked::after {
    display: flex;
  }
}
</style>
