<template>
  <div class="home">
    <h1>Projects</h1>
    <FilterNav @filterValue="current=$event" :current="current"></FilterNav>
    <div v-for="project in filterProjects" :key="project.id">
      <single-project :project="project" @delete="deleteProject" @complete="completeProject"></single-project>
    </div>
  </div>
</template>

<script>
import FilterNav from '../components/FilterNav'
import SingleProject from '../components/SingleProject.vue'

export default {
  name: 'Home',
  components: {
    FilterNav,
    SingleProject
  },
  data(){
    return {
      projects:[], //[{…}, {…}, {…}]
      current:"all"
    }
  },
  computed:{
    filterProjects(){
      if(this.current==="complete"){
        return this.projects.filter(project=>{
          return project.complete
        })
      }
      if(this.current==="ongoing"){
        return this.projects.filter(project=>{
          return !project.complete
        })
      }
      return this.projects;
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
