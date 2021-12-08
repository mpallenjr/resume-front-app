<template>
  <div class="home">

    <div class="card w-100" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">{{studentIndex.first_name}} {{studentIndex.last_name}} </h5>
    <h6 class="card-subtitle mb-2 text-muted">{{studentIndex.email}}</h6>
    <h6 class="card-subtitle mb-2 text-muted">{{studentIndex.phone_number}}</h6>
    <p class="card-text">{{studentIndex.bio}}</p>
    <a href="#" class="card-link">{{studentIndex.linkedin_url}}</a>
    <a href="#" class="card-link">{{studentIndex.twitter_handle}}</a>
    <a href="#" class="card-link">{{studentIndex.resume_url}}</a>
    <a href="#" class="card-link">{{studentIndex.github_url}}</a>
    <a href="#" class="card-link">{{studentIndex.website_url}}</a>
  </div>
  <div class="card w-100" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title"> Expierence</h5><h4>{{experiencesIndex.company_name}} | {{experiencesIndex.job_title}}</h4>
    <h6 class="card-subtitle mb-2 text-muted">{{experiencesIndex.start_date}} - {{experiencesIndex.end_date}}</h6>
    <p class="card-text">{{experiencesIndex.details}}</p>
  </div>
  <div class="card w-100" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Capstone</h5><h4>{{capstonesIndex.name}} </h4>
    <h6 class="card-subtitle mb-2 text-muted">{{capstonesIndex.url}}</h6>
    <p class="card-text">{{capstonesIndex.description}}</p>
  </div>
  <div class="card w-100" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title"> Education</h5><h4>{{educationsIndex.university_name}}</h4>
    <h6 class="card-subtitle mb-2 text-muted">{{educationsIndex.start_date}} - {{educationsIndex.end_date}}</h6>
    <h6> {{educationsIndex.degree}} </h6>
    <p class="card-text">{{educationsIndex.details}}.</p>
  </div>
  <div class="card w-100" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Skills</h5>
    <h6 class="card-subtitle mb-2 text-muted">{{skillsIndex.skill_name}}</h6>
  </div>
</div>
</div>
</div>
</div>
</div>
  </div>
</template>

<style></style>

<script>
import axios from 'axios';
  export default {
    data: function () {
      return {
        message: "Welcome to Vue.js!",
        studentIndex: [],
        experiencesIndex: [],
        capstonesIndex: [],
        educationsIndex: [],
        skillsIndex: []



      };
    },
    created: function () {
axios.get("http://localhost:3000/students/1").then(response => {
  console.log(response.data)
  this.studentIndex = response.data
}),
axios.get("http://localhost:3000/experiences/1").then(response => {
  console.log(response.data)
  this.experiencesIndex = response.data
}),
axios.get("http://localhost:3000/capstones/1").then(response => {
  console.log(response.data)
  this.capstonesIndex = response.data
}),
axios.get("http://localhost:3000/educations/1").then(response => {
  console.log(response.data)
  this.educationsIndex = response.data
}),
axios.get("http://localhost:3000/skills/1").then(response => {
  console.log(response.data)
  this.skillsIndex = response.data
})
    },
    methods: {},
  };
</script>
