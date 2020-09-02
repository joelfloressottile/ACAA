<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
@font-face {
  font-family: "Open Sans";
  src: local("OpenSans"),
    url(./assets/fonts/OpenSans/OpenSans-Regular.ttf) format("truetype");
}

@font-face {
  font-family: "PT Serif";
  src: local("PTSerif"),
    url(./assets/fonts/PT_Serif/PTSerif-Regular.ttf) format("truetype");
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

html,
body {
  margin: 0px !important;
  padding: 0px !important;
  background: var(--platinum);
  max-width: 100%;
}
</style>
