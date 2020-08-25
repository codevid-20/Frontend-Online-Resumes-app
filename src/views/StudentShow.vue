<template>
  <div class="StudentIndex">

    <h2> Photo: {{ student.photo }}</h2>
 
    <h1> {{ student.first_name }} {{ student.last_name }}</h1>
    <h3> {{ student.email }} | {{ student.phone_number }}</h3>
    <p> Short Bio: {{ student.short_bio }}</p>
    
    <h2> Experiences: </h2>

    <h2> links: </h2>
    <h2> Online Resume: {{ student.online_resume }}</h2>
    <h2> Linkedin URL: {{ student.linkedin_url }}</h2>
    <h2> Twitter Handle: {{ student.twitter_handle }}</h2>
    <h2> Personal Blog: {{ student.personal_blog }}</h2>
    <h2> Github URL: {{ student.email }}</h2>
    

    



  
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Individual Student",
      student: {},
    };
  },
  created: function () {
    this.studentIndex();
  },
  methods: {
    studentIndex: function () {
      console.log("Student Index Goes HERE:");
      axios.get(`/api/students/${this.$route.params.id}`).then((response) => {
        console.log(response);
        this.student = response.data;
      });
    },
  },
};
</script>
