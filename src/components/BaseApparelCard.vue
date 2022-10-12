<template>
  <div class="apparel-card">
    <div class="apparel-info">
      <div class="apparel-logo">
        <img src="@/assets/img/logo.svg" alt="" @dragstart.prevent />
      </div>
      <div class="apparel-title"><span>WE'RE</span>COMING SOON</div>
      <div class="apparel-body">
        Hello fellow shoppers! Were currently building our new fashion store.
        Add your email below to stay up-to-date with announcements and our
        launch deals
      </div>
      <div class="apparel-footer">
        <input type="email" placeholder="Email address" />
        <button>
          <img src="@/assets/img/icon-arrow.svg" alt="" />
        </button>
      </div>
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
@import "@/assets/less/variables.less";
.apparel-card {
  width: 970px;
  display: grid;
  grid-auto-flow: column;
  grid-template-rows: 535px;
  grid-template-columns: 4fr 3fr;
  border-radius: 6px;
  background-image: linear-gradient(
    135deg,
    hsl(0, 0%, 100%),
    hsl(0, 100%, 98%)
  );
  box-shadow: 3px 4px 7px 3px rgba(0, 0, 0, 0.2);
}

.apparel-info {
  display: grid;
  grid-template-rows: repeat(4, 120px);
  grid-auto-columns: 300px;
  justify-items: start;
  align-items: flex-start;
  padding: 2.5rem 3rem 3rem 7rem;
  background-image: url("../assets/img/bg-pattern-desktop.svg");
}

.apparel-img img {
  width: 100%;
  height: 100%;
}

.apparel-logo {
  color: @softRed;
}

.apparel-logo img {
  width: 110px;
  height: 25px;
}

.apparel-title {
  display: flex;
  flex-direction: column;
  text-align: left;
  font-size: 2.7rem;
  font-weight: 600;
  letter-spacing: 10px;
}
.apparel-title span:first-child {
  font-size: 2.7rem;
  color: @desaturatedRed;
  font-weight: 300;
}

.apparel-body {
  font-size: 12px;
  margin-top: 25px;
  text-align: left;
  line-height: 1.2rem;
  color: @desaturatedRed;
}

.apparel-footer {
  width: 100%;
  display: flex;
  padding-bottom: 20px;

}
.apparel-footer input {
  width: 100%;
  padding: 8px;
  border-radius: 30px;
  border-top: 1px solid #b1b1b1;
  border-left: 1px solid #b1b1b1;
  border-bottom: none;
  border-right: none;
}

@media (min-width: 1440px) {
  .apparel-card {
    min-width: 800px;
  }
}
</style>
