<template>
  <button @click="onClick()" :style="{ background: color }">{{ text }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      this.$emit('show-add-task')
    },
  },
};
</script>

<style>
button {
  text-align: center;
  padding: 5px;
  float: right;
}
</style>
