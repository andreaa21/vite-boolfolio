<script>

import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue';


export default {
  name: 'App',
  components:{
    ProjectCard
  },
  data(){
    return{
      baseUrl: 'http://127.0.0.1:8000/api/',
      projects: []
    }
  },
  methods:{
    getApi(){
      axios.get(this.baseUrl + 'projects')
          .then(result => {
            this.projects = result.data.projects;
            console.log(this.projects);
          })
    }
  },
  mounted(){
    this.getApi();
  }
}
</script>

<template>
  <div class="container">
    <div v-for="project in projects" :key="project.id">
      <h2>{{ project.name }}</h2>
      <p>{{ project.summary}}</p>
    </div>
  </div>
</template>



<style lang="scss">
@use './style/general.scss';
</style>
