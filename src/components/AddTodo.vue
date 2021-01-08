<template>
  <div>
    <h3>Add Todo</h3>
    <div class="add">
      <form @submit="onSubmit">
        <input type="text" v-model="title" placeholder="Add Todo" />
        <input type="submit" value="Submit" />
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  data() {
    return { title: "" };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #39a0ed;
  border-top-left-radius: 4px;
  border-bottom-left-radius: 4px;
  outline: 0;
}

input[type="submit"] {
  flex: 2;
  background: #39a0ed;
  color: #fff;
  border: 1px #39a0ed solid;
  cursor: pointer;
  border-top-right-radius: 4px;
  border-bottom-right-radius: 4px;
  transition: opacity 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
}

input[type="submit"]:hover {
  opacity: 0.8;
}
</style>