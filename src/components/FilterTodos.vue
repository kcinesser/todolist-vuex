<template>
  <div>
    Filter Todos:
    <select @change="filterTodos($event)">
      <option value="200">200</option>
      <option value="100">100</option>
      <option value="50">50</option>
      <option value="20">20</option>
      <option value="10">10</option>
      <option value="5">5</option>
    </select>
    <button @click="filterComplete()" v-bind:class="{ active: filterStatus }">
      Hide Complete
    </button>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

export default {
  name: "FilterTodos",
  methods: mapActions(["filterTodos", "filterComplete"]),
  computed: mapGetters(["filterStatus"]),
};
</script>

<style scoped>
select {
  margin-top: 20px;
  padding: 6px;
  border: none;
  border-radius: 4px;
  margin-right: 5px;
}

button {
  background-color: #39a0ed;
  outline: 0;
  border: none;
  border-radius: 4px;
  padding: 6px;
  color: #fff;
  cursor: pointer;
  transition: all 0.4s cubic-bezier(0.075, 0.82, 0.165, 1);
}

.active {
  background-color: #35495e;
}
</style>