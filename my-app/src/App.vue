<template>
  <v-app id="app">
    <v-main>
      <bubble x="0" y="90vh" degree="80" />
      <bubble x="0" y="80vh" degree="180" />
      
      <bubble x="45vw" y="10vh" degree="270" />
      <bubble x="30vw" y="30vh" degree="0" />
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@400;600&display=swap");
#app {
  min-height: 100vh;
  min-width: 100vw;
}
.theme-text {
  color: #535cb5 !important;
}
.theme-elevation{
   --col: 82, 82, 203;
  box-shadow: 0px 4px 20px rgba(var(--col), 0.2) !important;
}
* {
  font-family: "Nunito", sans-serif !important;
}
</style>

<script>
import HelloWorld from "./components/HelloWorld";
import bubble from "./components/bubble";

export default {
  name: "App",

  components: {
    HelloWorld,
    bubble,
  },

  data: () => ({
    //
  }),
};
</script>
