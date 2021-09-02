<template>
  <div class="header">
    <h1 class="center">{{ title }}</h1>
    <div class="row">
      <div col-8>
        <AddTask @addTask="addTask" />
      </div>
      <div col-4>
        <Button text="Add Task" color="lightgreen" />
      </div>
    </div>
    <Tasks
      @toggle-alarm="toggleAlarm"
      @delete-task="deleteTask"
      :tasks="tasks"
    />
  </div>
</template>

<script>
import Button from "./Button";
import Tasks from "./Tasks";
import AddTask from "./AddTask";
export default {
  el: "#header",
  props: {
    title: {
      type: String,
      default: "Task Tracker", //If title is not passed then this will print.
    },
  },
  data() {
    return {
      tasks: [],
    };
  },
  components: {
    Button,
    Tasks,
    AddTask,
  },
  methods: {
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
    deleteTask(id) {
      if (confirm("Are you sure?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
    toggleAlarm(id) {
      this.tasks = this.tasks.map((task) =>
        task.id == id ? { ...task, alarm: !task.alarm } : task
      );
    },
  },
  created() {
    // it is a method ex: this is used to load html at the starting or when page loads
    this.tasks = [
      {
        id: 1,
        text: "Text1",
        day: "Monday",
        reminder: "Day 1 Monday 12 ist",
        alarm: true,
      },
      {
        id: 2,
        text: "Text2",
        day: "Tuesday",
        reminder: "Day 2 Tuesday 12 ist",
        alarm: true,
      },
      {
        id: 3,
        text: "Text3",
        day: "Wednesday",
        reminder: "Day 3 Wednesday 12 ist",
        alarm: false,
      },
      {
        id: 4,
        text: "Text4",
        day: "Thrusday",
        reminder: "Day 4 Thrusday 12 ist",
        alarm: true,
      },
    ];
  },
};
</script>

<style scoped>
.header {
  margin-bottom: 10px;
}
.button {
  padding: 5px;
}
</style>
