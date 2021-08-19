<template>
  <div class="container">
    <h1>Task Tracker</h1>
    <p>{{ title }}</p>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: ["title"],
};
</script>

<style scoped >
header {
  background-color: darkorange;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 10px;
}
</style>