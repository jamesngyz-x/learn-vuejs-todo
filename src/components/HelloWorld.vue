<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <alert mode="primary">First</alert>
    <alert mode="danger">Second</alert>
    <alert mode="success">Third</alert>
    <alert mode="primary">Fourth</alert>

    <div>
      <input type="text" v-model="lastname" placeholder="Your name, please?" />
      <p>Welcome, {{ lastname }}</p>

      <button @click="clicky">Click me</button>
      <input type="text" @keyup.enter="entery" />

      <ol>
        <li :key="student.id" v-for="student in students">
          {{ student.name }}
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      lastname: "",
      students: [
        { id: 1, name: "Aber" },
        { id: 2, name: "Fitch" },
        { id: 3, name: "Dan" },
      ],
    };
  },
  methods: {
    clicky: function () {
      console.log("clicked!!");
    },
    entery: function () {
      console.log("entered!!");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
