<template>
    <nav class="main-nav">
        <router-link to="/">Projects</router-link>
        <router-link :to="{name:'AddProject'}">Add Project</router-link>
    </nav>
</template>

<script>
export default {

}
</script>

<style>
    .main-nav{
        text-align: center;
        margin: 40px 0;
    }
    .main-nav a{
        text-decoration: none;
        margin: 0 10px;
        color: grey;
    }
    .router-link-active{
        border-bottom: 1px solid grey;
        padding-bottom: 4px;
    }
</style>