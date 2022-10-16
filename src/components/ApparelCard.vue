<template>
  <div class="apparel-card">
    <div class="apparel-info">
      <div class="apparel-logo">
        <img src="@/assets/img/logo.svg" alt="" @dragstart.prevent />
      </div>
      <div class="apparel-img-mobile">
        <img src="@/assets/img/hero-mobile.jpg" alt="" />
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
            type="text"
            placeholder="Email address"
            v-model="email"
            @input="removeInvalidOnInput"
          />
          <img
            src="@/assets/img/icon-error.svg"
            alt=""
            class="error"
            v-if="isInvalidEmail"
          />
          <button @click="checkEmail">
            <img src="@/assets/img/icon-arrow.svg" alt="" />
          </button>
        </form>
        <div class="not-required" v-if="isInvalidEmail">
          <span>Please provide a valid email!</span>
        </div>
      </div>
    </div>
    <div class="apparel-img-desktop">
      <img src="@/assets/img/hero-desktop.jpg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "apparel-card",
  data() {
    return {
      email: "",
      isInvalidEmail: false,
    };
  },
  methods: {
    removeInvalidOnInput() {
      if (this.isInvalidEmail && this.email.length === 0) {
        this.isInvalidEmail = false;
      }
    },
    checkEmail() {
      const emailRegex = /^[A-Za-z0-9_!#$%&'*+\/=?`{|}~^.-]+@[A-Za-z0-9.-]+$/gm;
      if (this.email.length === 0 || !emailRegex.test(this.email)) {
        this.isInvalidEmail = true;
      } else {
        this.email = "";
        this.isInvalidEmail = false;
      }
    },
  },
};
</script>

<style lang="less" scoped>
@import "@/assets/less/apparelCard.less";
</style>
