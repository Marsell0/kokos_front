<template>
  <div class="login" v-show="showModal">
    <div class="login__wrapper">
      <div class="login__title">
        <p>Вход</p>
        <p @click="closeModal">&#10006;</p>
      </div>
      <form class="login__l-form" method="post">
        <input
          class="l-form__input"
          type="email"
          placeholder="email"
          required
        />
        <input
          class="l-form__input"
          type="password"
          placeholder="password"
          required
        />
        <button class="l-form__btn">Войти</button>
      </form>
      <div class="login__subtitle">
        <p>Зарегестрироваться</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
let showModal = false;

const props = defineProps({
  showModal: false,
});

function closeModal() {
  showModal = false;
  console.log(showModal);
}
</script>

<style scoped>
.login {
  border-radius: 35px;
  background: #171717;
  padding: 15px;
  min-width: 420px;
  max-width: 480px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
}
.login__wrapper {
  display: flex;
  flex-direction: column;
}
.login__title {
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  color: #fff;
  font-family: Noto Sans;
  font-size: 30px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  padding-bottom: 70px;
}
.login__subtitle {
  color: #4f4f4f;
  font-family: Noto Sans;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  margin-bottom: 50px;
}
.login__l-form {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.l-form__input {
  margin: 10px 0px;
  border-radius: 10px;
  border: 1px solid #8ac0ff;
  background: #fff;
  padding: 20px 36px;
}
.l-form__btn {
  border-radius: 8px;
  background: #e6533c;
  display: inline-flex;
  padding: 20px 75px;
  justify-content: center;
  align-items: center;
  gap: 10px;
  color: #fff;
  margin: 30px 0px;
}
</style>
