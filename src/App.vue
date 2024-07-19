<script>
import axios from 'axios';


export default {
  name: 'App',

  data() {
    return {
      projects: ''
    }
  },

  mounted() {

    axios
      .get('http://127.0.0.1:8000/api/projects')
      .then(response => {
        console.log(response);
        this.projects = response.data.projects
        console.log(this.projects)

      })

  },

}
</script>

<template>
  <h1>Welcomee</h1>

  <div class="container">

    <div class="card" v-for="project in projects.data">
      {{ project.name }}
    </div>
  </div>


</template>

<style>
.testo {
  color: green;
  font-size: 30px;
}
</style>
