<template>
  <div class="header">
    <h1>{{ title }}</h1>
    <Button text='Add Task' color="lightgreen"/>
    <Button text='Update Task' color="yellow"/>
    <Button text='Delete Task' color="crimsonred"/>
    <Tasks :tasks="tasks"/>
  </div>
</template>

<script>
import Button from './Button'
import Tasks from './Tasks'
export default {
  el: '#header',
  props:{
    title: {
      type: String,
      default: "Task Tracker" //If title is not passed then this will print.
    }
  },
  data(){
    return {
      tasks: []
    }
  },
  components:{
    Button,
    Tasks
  },
  created(){
    // it is a method ex: this is used to load html at the starting or when page loads
    this.tasks=[
      {
        id: 1,
        text: 'Text1',
        day: 'Monday',
        reminder: 'Day 1 Monday 12 ist',
        alarm: true
      },
      {
        id: 2,
        text: 'Text2',
        day: 'Tuesday',
        reminder: 'Day 2 Tuesday 12 ist',
        alarm: true
      },
      {
        id: 3,
        text: 'Text3',
        day: 'Wednesday',
        reminder: 'Day 3 Wednesday 12 ist',
        alarm: false
      },
      {
        id: 4,
        text: 'Text4',
        day: 'Thrusday',
        reminder: 'Day 4 Thrusday 12 ist',
        alarm: true
      }
    ]
  }
};
</script>

<style scoped >
header {
  background-color: darkorange;
  display: flex;
  
  justify-content: center;
  align-items: center;
  margin-bottom: 10px;  
  text-align: center;
}
</style>