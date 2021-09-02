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
  padding: 0.5em;
  float: right;
  word-break: break-all;
  font-size: 0.8em;
  font-size-adjust: inherit;
  font-weight: 600;
}
</style>
