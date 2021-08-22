<template>
  <Home />
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "App",
  components: {
    Home,
  },
};
</script>

<style>
@font-face {
  font-family: "Abril";
  src: url("../public/assets/AbrilFatface-Regular.ttf") format("truetype");
}

@font-face {
  font-family: "Kanit";
  src: url("../public/assets/Kanit-Light.ttf") format("truetype");
}

body {
  background: #406a8d;
  color: white;
}
#app {
  font-family: Kanit, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  margin-top: 60px;
}

h1,
h2,
h3 {
  font-family: Abril, Avenir, Helvetica, Arial, sans-serif;
  font-weight: normal;
  color: white;
  font-size: 36px;
}

.button {
  margin: 20px auto;
  border: none;
  background: rgb(23, 58, 92);
  color: white;
  padding: 12px 20px;
  border-radius: 2px;
  box-shadow: 1px 2px 5px rgba(0, 0, 0, 0.3);
  transition: all 200ms ease;
  font-size: 16px;
  width: 240px;
  box-sizing: border-box;
  text-decoration: none;
}

.button:active {
  transform: scale(0.98);
  box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.3);
}

.button:hover {
  text-decoration: underline;
  cursor: pointer;
}

.button:disabled {
  opacity: 0.5;
  cursor: default;
  text-decoration: none;
}
</style>
