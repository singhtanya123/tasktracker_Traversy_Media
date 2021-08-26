<template>
  <div class="container">
    <Header title="Hello, let's get started" /> <!--component with prop title-->
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
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
header{
  display: flex;
  flex-direction: column;
}
.container{
  box-sizing: border-box;
  border: 1px solid blue;
  padding: 30px;
  min-height: 300px;
}
</style>