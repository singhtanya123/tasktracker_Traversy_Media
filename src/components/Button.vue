<template>
  <button @click="onClick()" :style="{ background: color }" >{{ text }}</button>
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
      console.log("button click");
    },
  },
};
</script>

<style>
button {
  margin-top:-5em;
  text-align: center;
  padding: 5px;
  color: red;
  float: right;
}
</style>
