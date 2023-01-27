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
      <h1>Elenco Progetti</h1>
  <div class="container">


      <ProjectCard
        v-for="project in projects" :key="project.id"
        :project = "project"
      />
    </div>
</template>



<style lang="scss">

@use './style/general.scss';

.container{
  width: 80%;
  max-width: 1200px;
  margin: 2rem auto;
  display: flex;
  flex-wrap: wrap;
}

body{
  background-color: rgb(77, 104, 153);
}
h1{
  color: white;
}
</style>
