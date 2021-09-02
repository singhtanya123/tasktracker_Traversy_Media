<template>
  <div
    @dblclick="$emit('toggle-alarm', task.id)"
    :class="[task.alarm ? 'reminder' : '', 'task']"
  >
    <h5>
      {{ task.text }}
      <i @click="onDelete(task.id)" class="fas fa-times"></i>
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
      this.$emit("delete-task", id);
    },
  },
};
</script>

<style scoped>
.task {
  background: #999da0;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 8px solid rgb(31, 165, 31);
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
