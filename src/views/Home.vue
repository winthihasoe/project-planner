<template>
  <div class="home">
    <h1>Home</h1>
    <div v-for="project in projects" :key="project.id">
      <single-project :project="project" @delete="deleteProject" @complete="completeProject"></single-project>
    </div>
  </div>
</template>

<script>
import SingleProject from '../components/SingleProject.vue'

export default {
  name: 'Home',
  components: {
    SingleProject
  },
  data(){
    return {
      projects:[] //[{…}, {…}, {…}]
    }
  },
  methods:{
    deleteProject(id){
      this.projects=this.projects.filter(project=>{
        return project.id!=id;
      })
    },
    completeProject(id){
      let findProject=this.projects.find(project=>{
        return project.id===id;
      });
      findProject.complete=!findProject.complete
    }
  },
  mounted(){
    fetch('http://localhost:3000/projects')
    .then((response)=>{
      return response.json()
  })
    .then((datas)=>{
      this.projects=datas
  })
    .catch((err)=>{
      console.log(err);
    })
  }
}
</script>
