<template>
  <h1>Add Project</h1>
  <form @submit.prevent="addProject">
      <label for="">Project Title</label>
      <input type="text" v-model="title">
      <label for="">Project Detail</label>
      <input type="text" v-model="detail">
      <button>Add Project</button>
  </form>
</template>

<script>
export default {
    deta(){
        return {
            title:"",
            detail:""
        }
    },
    methods:{
        addProject(){
            fetch("http://localhost:3000/projects",{
                method:"POST",
                headers:{
                    "Content-Type":"application/json"
                },
                body:JSON.stringify(
                    {
                        title:this.title,
                        detail:this.detail,
                        complete:false
                    }
                )
            })
            .then(()=>{
                //redirect
                this.$router.push("/");
            })
            .catch((err)=>{
                console.log(err);
            })

        }
    }
}
</script>

<style scoped>
    
    form{
        background-color: white;
        padding: 20px;
        border-radius: 10px;
    }
    label{
        text-transform: uppercase;
        font-size: 14px;
        display: block;
        letter-spacing: 1px;
        font-weight: bold;
        margin: 30px 0 10px 0;
        text-align: left;
    }
    input{
        display: block;
        box-sizing: border-box;
        border: 0;
        border-bottom: 1px solid #ddd;
        width: 100%;
    }
    button{
        margin: 20px;
        background-color: indigo;
        color: white;
        padding: 5px 10px;
        border-radius: 8px;
    }
</style>