<template>
    <div class="project">
        <div class="flexing">
            <div @click="showDetail=!showDetail">
                <h3>{{project.title}}</h3>
            </div>
            <div>
                <span class="material-icons">
                delete
                </span>
                <span class="material-icons">
                edit
                </span>
                <span class="material-icons">
                done
                </span>
            </div>
        </div>
        
        <p v-if='showDetail'>{{project.detail}}</p>

    </div>
</template>

<script>
export default {
    props:["project"],
    data(){
        return {
            showDetail:false
        }
    }
}
</script>

<style>
    .project{
        background-color: #f2f2f2;
        padding: 15px;
        margin: 10px;
        text-align: left;
    }

    h3{
        color: indigo;
        cursor: pointer;

    }

    .flexing{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    span{
        margin-left: 10px;
    }
    span:hover{
        color: #777;
        cursor: pointer;
    }
</style>