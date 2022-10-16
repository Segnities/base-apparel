<template>
  <div class="App">
      <apparel-card/>
  </div>
</template>

<script>
import ApparelCard from "@/components/ApparelCard.vue";
export default {
  name: "App",
  components: {
    ApparelCard
  }
};
</script>

<style lang="less">
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400;600&display=swap');
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
}

.App {
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}


</style>
