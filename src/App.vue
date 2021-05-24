<template>
  <img
    alt="AJ-Wi"
    src="https://github.com/AJ-Wi/AJ-Wi.github.io/blob/master/images/AJ-Wi.svg"
  />
  <h1>AJ Web Components Vue</h1>
  <h2>Custom Inputs!</h2>
  <BaseInput v-model="text" name="text" type="text">text</BaseInput>
  {{ text }}
  <br />
  <br />
  <BaseInput v-model="pass" name="pass" type="password">password</BaseInput>
  <br />
  <h2>Custom Images!</h2>
  <training level="1" sublevel="1"></training>
  <training level="2" locked="false" sublevel="2" bike="2"></training>
  <training level="3" sublevel="3" bike="3"></training>
  <training active="true" bike="1"></training>
  <training></training>
</template>

<script>
import BaseInput from "@/components/BaseInput.vue";
import training from "@/components/BaseSVG.vue";

export default {
  name: "App",
  components: {
    BaseInput,
    training,
  },
  data() {
    return {
      text: "",
      pass: "",
    };
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}
#app {
  max-width: 400px;
  margin: 0 auto;
  line-height: 1.4;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: blue;
}
h1 {
  text-align: center;
}
</style>
