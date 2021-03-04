<template>
    <div class="filter-nav">
        <button @click="filterBy('all')" :class="{active : current==='all'}">all</button>
        <button @click="filterBy('complete')" :class="{active : current==='complete'}">complete</button>
        <button @click="filterBy('ongoing')" :class="{active : current==='ongoing'}">ongoing</button>
    </div>
</template>

<script>
export default {
    methods:{
        filterBy(value){
            this.$emit('filterValue',value)
        }
    },
    props:['current']
}
</script>

<style scoped>
    .filter-nav{
        text-align: left;
    }

    .filter-nav button{
        background: none;
        border: none;
        text-transform: uppercase;
        font-size: 12px;
        outline: none;
        margin-right: 10px;
        font-weight: bold;
        color: #bbb;
        letter-spacing: 1px;
        cursor: pointer;
    }

    button.active{
        color: #333;
    }
</style>