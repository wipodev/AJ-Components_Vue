<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <h2>Custom Inputs!</h2>
  <Baseinput type="text" name="user">User</Baseinput>
  <Baseinput type="password" name="pass">password</Baseinput>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Baseinput from "./components/Baseinput.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Baseinput,
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
</style>
