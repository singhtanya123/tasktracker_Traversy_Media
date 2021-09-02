<template>
  <div class="container">
    <Header title="Hello, let's get started" />
    <!--component with prop title-->
    <!--<hello-world msg="Welcome to vue  i am helloworld"></hello-world>  -->
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld";
import Header from "./components/Header";

export default {
  name: "App",
  components: {
    //    HelloWorld,
    Header,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 20px;
  margin-left: 1em;  
  font-weight: 550;
}
.addTask {
  margin-left: 2px;
}
.container {
  box-sizing: border-box;
  padding: 5px;
  min-height: 300px;
}
.center {
  text-align: center;
}
.right {
  float: right;
}
.margintop {
  margin-top: 2em;
}
</style>
