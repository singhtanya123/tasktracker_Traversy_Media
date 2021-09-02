<template>
  <!--form created and bind with @submit used in type input (save button) to a function onSubmit-->
  <form @submit="onSubmit" class="add-task">
    <div class="form-control">
      <label class="task-label">Add Task</label>
      <input
        class="col-md-8"
        type="text"
        name="text"
        placeholder="Add Task"
        v-model="text"
      />
      {{ text }}
    </div>
    <div class="form-control">
      <label class="task-label">Add Day</label>
      <input
        class="col-md-8"
        type="text"
        name="day"
        placeholder="Add Day"
        v-model="day"
      />
    </div>
    <div class="form-control">
      <label class="task-label">Add Reminder</label>
      <input
        class="col-md-8"
        type="text"
        name="reminder"
        placeholder="Set Reminder: 31/aug/2021"
        v-model="reminder"
      />
    </div>
    <div class="form-control">
      <label class="task-label">Add Alarm</label>
      <select
        class="select-radio col-md-8"
        name="alarm"
        placeholder="Set Alarm"
        v-model="alarm"
      >
        <option value="true">True</option>
        //Give in value which is about to pass it, can use these values by name.
        <option value="false">False</option>
      </select>
    </div>
    <input type="submit" value="Save Task" class="save-btn" />
  </form>
</template>

<script>
export default {
  el: "#AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: "",
      alarm: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      if (!this.text) {
        alert("Please add a task");
        return;
      }
      if (!this.day) {
        alert("Please add a day");
        return;
      }
      if (!this.reminder) {
        alert("Please add a reminder");
        return;
      }
      const newTask = {
        id: Math.floor(Math.random()),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
        alarm: this.alarm,
      };

      this.$emit("add-task", newTask);

      (this.text = ""),
        (this.day = ""),
        (this.reminder = ""),
        (this.alarm = false);
    },
  },
};
</script>

<style scoped>
.add-task {
  margin-bottom: 15px;
}
.form-control {
  margin: 5px;
  padding: 5px;
}
.task-label {
  margin: 10px;
  padding: 10px;
}
.save-btn {
  margin: 20px;
  padding: 10px;
  color: whitesmoke;
  background-color: black;
}
input,
select {
  -ms-box-sizing: content-box;
  -moz-box-sizing: content-box;
  -webkit-box-sizing: content-box;
  box-sizing: content-box;
}
</style>
