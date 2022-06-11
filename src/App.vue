<template>
  <div class="app-wrapper">
    <h1>We keep your TODO<small>s</small> alive</h1>
    <h2>sunday</h2>
    <h4><sub> 3-6-2022</sub></h4>
    <Add></Add>
  </div>
</template>

<script>
import Add from "./components/Todo.vue";

export default {
  name: "App",
  components: {
    Todo,
  },
};
</script>

<style  scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-image: linear-gradient(#00c6ff 0%, #0072ff 100%);
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
  max-height: 100vh;
  overflow: hidden;
  font-family: "Source Sans Pro", sans-serif;
}

#app {
  background-image: linear-gradient(#00c6ff 0%, #0072ff 100%);
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
  max-height: 100vh;
  overflow: hidden;
  font-family: "Source Sans Pro", sans-serif;
}
.app-wrapper {
  width: 60%;
  max-width: 450px;
  min-width: 400px;
  min-height: 250px;
  margin: 30px auto;
  padding: 10px;
  background-color: #fff;
  border-radius: 3px;
  font-family: "Source Sans Pro", sans-serif;
  font-weight: 100;
}

h1 {
  text-align: center;
  margin: 0;
  font-weight: 600;
  font-family: "Pacifico", cursive;
  color: #3e4451;
}
h2 {
  margin: 15px 0 10px 20px;
  display: inline-block;
  color: #61afef;
}

h4 {
  display: inline-block;
  margin: 0;
  font-weight: bold;
}

h4 sub {
  color: #61afef;
  font-weight: 400;
}
</style>
