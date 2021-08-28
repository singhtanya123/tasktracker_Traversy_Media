<template>
  <div :class="[task.alarm ? 'reminder' : '', 'task']">
    <h5>
      {{ task.text }} <i @click="onDelete(task.id)" class="fas fa-times"></i>
      <!--delete-->
    </h5>
    <p class="reminder">{{ task.reminder }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      console.log(id);
    },
  },
};
</script>

<style scoped>
.task {
  background: hotpink;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}

.task h5 {
  display: flex;
  justify-items: left;
  text-align: left;
  justify-content: space-between;
}
p {
  text-align: left;
}
</style>
