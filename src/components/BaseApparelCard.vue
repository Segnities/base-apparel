<template>
  <div class="apparel-card">
    <div class="apparel-info">
      
    </div>
    <div class="apparel-img">
      <img src="../assets/img/hero-desktop.jpg" alt="" @dragstart.prevent />
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseApparelCard",
};
</script>

<style lang="less" scoped>
.apparel-card {
  width: 970px;
  display: grid;
  grid-template-rows: 560px;
  grid-template-columns: 4fr 3fr;
  border-radius: 6px;
  background-image: linear-gradient(135deg, hsl(0, 0%, 100%), hsl(0, 100%, 98%));
  box-shadow: 3px 4px 7px 3px rgba(0, 0, 0, 0.2);
}

.apparel-img img {
    width: 100%;
    height: 100%;
  }

@media (min-width: 1440px) {
  .apparel-card {
    min-width: 800px;
  }

}
</style>
