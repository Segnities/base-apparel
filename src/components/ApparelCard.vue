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
@import "@/assets/less/variables.less";

.apparel-card {
  width: 970px;
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

.apparel-img-desktop img {
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
  width: 15px;
  height: 15px;
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

.apparel-img-mobile {
  display: none;
}

@media (min-width: 1440px) {
  .apparel-card {
    min-width: 800px;
  }
}

@media (max-width: 950px) {
  .apparel-card {
    max-width: 850px;
  }
}

@media (max-width: 840px) {
  .apparel-card {
    max-width: 750px;
  }
}

@media (max-width: 784px) {
  .apparel-card {
    width: 100%;
    min-height: 100vh;
    align-items: center;
    display: grid;
    grid-template-rows: 1fr 200px;
    grid-template-columns: 1fr;
  }

  .apparel-info {
    width: 100%;
    padding: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .apparel-logo {
    width: 100%;
    padding: 4rem 2rem;
    display: flex;
    justify-content: flex-start;
  }

  .apparel-title {
    width: 100%;
    padding: 0rem 2rem;
    margin-top: 5rem;
    margin-bottom: 1rem;
    text-align: center;
  }

  .apparel-body {
    text-align: center;
    padding: 0rem 2rem;
    font-size: 13px;
    margin-top: 0;
    margin-bottom: 25px;
  }

  .apparel-footer {
    width: 100%;
  }
  .form-email {
    width: 100%;
  }

  .apparel-img-mobile {
    width: 100%;
    display: block;
    padding: 0;

  }

  .apparel-img-mobile img {
    width: 100%;
    padding: 0rem 0rem;
  }

  .form-email {
    width: 100%;
    margin: 30px 0;
    padding: 0;
  }

  .form-email input {
    padding: 18px 20px;
  }

  .form-email input::placeholder {
    font-size: 14px;
  }

  .form-email button {
    padding: 18px 30px;
    border-radius: 40px;
  }

  .form-email button img {
    width: 16px;
    height: 16px;
  }

  .apparel-img-desktop {
    display: none;
  }
}
</style>
