<script setup></script>
<template>
  <div>
    <div class="heading activ">
      <div class="input">
        <img src="../../assets/FAVICON-32X32.PNG" alt="" />
        <input type="text" placeholder="Create a new todo" autofocus />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.heading {
  color: white;

  .input {
    width: 635px;
    padding: 15px;
    display: flex;
    background: white;
    border-radius: 5px;

    img {
      opacity: 0.5;
    }

    input {
      width: 635px;
      background: transparent;
      outline: none;
      border: none;
      margin-left: 10px;
      font-size: 19px;
      color: hsl(235, 19%, 35%);
    }
  }

  &.active {
    .input {
      background: hsl(235, 24%, 19%);
      input {
        color: hsl(234, 39%, 85%);
      }
    }
  }
}
</style>
