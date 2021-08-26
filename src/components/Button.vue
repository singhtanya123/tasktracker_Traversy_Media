<template>
    <button @click="onClick()" :style="{background:color}"> {{text}}</button>
</template>
<script>
export default {
    name: 'Button',
    props:{
        text: String,
        color: String
    },
    methods:{
        onClick(){
            console.log('button click');
        }
    }
}
</script>

<style  scoped>
button{
    margin: 10px;
}
</style>
