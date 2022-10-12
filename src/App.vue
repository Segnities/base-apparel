<template>
  <div class="App">

  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style lang="less">
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400;600&display=swap');
@import "./assets/less/variables.less";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Josefin Sans', 'Courier New', Courier, monospace, sans-serif;
  font-size: 16px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.App {
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: linear-gradient(), url('./assets/img/bg-pattern-desktop.svg');
}

</style>
