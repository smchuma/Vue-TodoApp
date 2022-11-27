<!-- <template>
  <div>
    <div class="heading activ">
      <div class="input">
        <img src="../../assets/FAVICON-32X32.PNG" alt="" />
        <input
          type="text"
          placeholder="Create a new todo"
          autofocus
          @keyup.enter="addTodo"
          @input="handleInput"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "TodoInput",
  props: ["addTodo", "newToDo"],

  data() {
    return {
      content: this.newToDo,
    };
  },

  methods: {
    handleInput(event) {
      this.$emit("handleInput", (this.content = event.target.value));
    },
  },
};
</script>
<style lang="scss">
@import "./TodoInput.scss";
</style> -->
