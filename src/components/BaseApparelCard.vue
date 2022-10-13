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
        <form class="form-email" @submit.prevent>
          <input
            type="email"
            placeholder="Email address"
            maxlength="25"
            v-model="email"
          />
          <img src="@/assets/img/icon-error.svg" alt="" class="error" />
          <button data-email-button="btn">
            <img src="@/assets/img/icon-arrow.svg" alt="" />
          </button>
        </form>
        <div class="not-required">
          <span>Please provide a valid email!</span>
        </div>
      </div>
    </div>
    <div class="apparel-img">
      <img src="@/assets/img/hero-desktop.jpg" alt="" @dragstart.prevent />
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseApparelCard",
  data() {
    return {
      email: "",
      isValidEmail: true,
    };
  },
};
</script>

<style lang="less" scoped>
@import "@/assets/less/variables.less";

.apparel-card {
  max-width: 970px;
  display: grid;
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
  padding: 2.5rem 3rem 3rem 6rem;
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
  font-size: 11px;
  margin-top: 25px;
  text-align: left;
  line-height: 1.2rem;
  color: @desaturatedRed;
}

.apparel-footer {
  width: 360px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.apparel-footer .form-email {
  width: 100%;
  align-items: center;
  display: flex;
}
.form-email input {
  width: 100%;
  padding: 10px 15px;
  border-radius: 30px;
  border-top: 1px solid #b1b1b1;
  border-left: 1px solid #b1b1b1;
  border-bottom: none;
  border-right: none;
}

.form-email input:focus-visible {
  outline: none;
}

.form-email input::placeholder {
  font-size: 11px;
  font-weight: 300;
  color: @desaturatedRed;
}

.form-email button {
  position: relative;
  right: 40px;
  padding: 12px 30px;
  border-radius: 20px;
  border: none;
  outline: none;
  cursor: pointer;
  background: linear-gradient(135deg, hsl(0, 80%, 86%), hsl(0, 74%, 74%));
  box-shadow: 0px 6px 6px 5px hsl(0 0% 0% / 7%);
}
.form-email button:hover {
  background: hsl(0, 80%, 86%);
  transform: scale(1.03);
  transition: transform 0.4s ease-in-out;
}

.apparel-footer .error {
  width: 12px;
  height: 12px;
  position: relative;
  right: 50px;
}

.form-email button img {
  width: 10px;
  height: 10px;
}

.not-required {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-top: 10px;
}
.not-required span {
  color: @desaturatedRed;
  font-size: 11px;
  margin-left: 25px;
}

@media (min-width: 1440px) {
  .apparel-card {
    min-width: 800px;
  }
}
@media (max-width: 950px) {
  .apparel-card {
    max-width: 750px;
  }
}

@media (max-width: 784px) {
  .apparel-card {
    max-width: 750px;
  }
}
</style>
