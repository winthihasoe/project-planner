<template>
  <h1>Add Project</h1>
  <form>
      <label for="">Project Title</label>
      <input type="text">
      <label for="">Project Detail</label>
      <input type="text">
      <button>Add Project</button>
  </form>
</template>

<script>
export default {

}
</script>

<style>
    
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