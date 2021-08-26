<template>
    <div :class="[task.alarm? 'reminder': '','task']">
        <h5>{{task.text}}
            <i @click="onDelete('{{task.id}}')" class="fas fa-times"></i>
        </h5>        
        <p  class="reminder">{{task.reminder}}</p>
    </div>
</template>

<script>
export default {
    name : 'Task',
    props:{
        task: Object
    },
    methods:{
        onDelete(){
            
        }
    }
}
</script>

<style >
.task {
    background:hotpink;
    margin: 5px;        
    padding: 10px 20px;
    cursor: pointer;
    min-block-size: 20px;
}
.task.reminder{
    border-left: 5px solid green;
}

.task h3{
    display: flex;
    justify-items: center;
    text-align: center;
    justify-content: space-between;
}
.task h3 i{
    padding-left: -100px;
    }
</style>
