<script>
export default {
  data() {
    return {
      name: "John Doe",
      status: "active",
      tasks: ["task1", "task2", "task3"],
      link: "http://www.google.com",
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === "active") {
        this.status = "pending";
      } else if (this.status === "pending") {
        this.status = "inactive";
      } else {
        this.status = "active";
      }
    },
  },
};
</script>

<template>
  <h1>{{ name }}</h1>
  <br />
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>
  <br />
  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" :key="task">
      {{ task }}
    </li>
  </ul>

  <!-- Long way of v-bind -->
  <a v-bind:href="link">GOOGLE</a>
  <!-- Short way of v-bind -->
  <a :href="link">GOOGLE</a>
  <!-- Toggle Status -->
  <!-- <button v-on:click="toggleStatus">Toggle Status</button> -->
  <button @click="toggleStatus">Toggle Status</button>
</template>
