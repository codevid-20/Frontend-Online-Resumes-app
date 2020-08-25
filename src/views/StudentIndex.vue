<template>
  <div class="StudentIndex">
    <h1>{{ message }}</h1>
    <div v-for="student in studentArray">
      <p><a v-bind:href="`/students/${student.id}`">{{ student.first_name }} {{ student.last_name }} </a> </p>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Student Index List:",
      studentArray: [],
    };
  },
  created: function () {
    this.studentIndex();
  },
  methods: {
    studentIndex: function () {
      console.log("Student Index Goes HERE:");
      axios.get("/api/students").then((response) => {
        console.log(response);
        this.studentArray = response.data;
      });
    },
  },
};
</script>
