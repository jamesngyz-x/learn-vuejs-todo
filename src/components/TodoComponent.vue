<template>
  <div>
    <h1>Todo</h1>
    <input
      type="text"
      placeholder="Input task name"
      v-model="inputText"
      @keydown.enter="add"
    />
    <button @click="add()">Add</button>
    <ul class="task-list">
      <li v-for="(task, index) in tasks" :key="index">
        <span>{{ task }}</span>
        <span class="remove-button" @click="remove(index)">x</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoComponent",
  data: function () {
    return {
      inputText: "",
      tasks: [],
    };
  },
  methods: {
    add: function () {
      if (this.inputText != "") {
        this.tasks.push(this.inputText);
        this.inputText = "";
      }
    },
    remove: function (id) {
      this.$delete(this.tasks, id);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.task-list {
  list-style-type: none;
  padding-inline-start: 0;
}
.remove-button {
  padding-left: 1rem;
}
.remove-button:hover {
  cursor: pointer;
}
</style>
