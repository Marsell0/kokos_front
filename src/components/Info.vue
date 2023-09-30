<template>
  <div class="info">
    <div class="info__wrapper">
      <div class="info__title">
        <p class="title__subtitle">ВАШИ ДАННЫЕ</p>
        <img
          src="../assets/img/dashboard/edit.svg"
          alt=""
          class="title__icon"
        />
      </div>
      <div v-if="role === 'company'" class="info__link">
        <img
          src="../assets/img/dashboard/link.svg"
          alt="link"
          class="link__icon"
        />
        <p class="link__text">{{ link }}</p>
      </div>
      <div class="info__block">
        <p class="block__title">Компания</p>
        <p class="block__subtitle">{{ companyName }}</p>
      </div>
      <div class="info__block">
        <p class="block__title">Отдел</p>
        <p class="block__subtitle">{{ partName }}</p>
      </div>
      <div class="info__block">
        <p class="block__title">Email</p>
        <p class="block__subtitle">{{ email }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

let role = ref("employee");
let companyName = ref("ООО Копатыч");
let partName = ref("Агро-сектор");
let email = ref("example@gmail.com");
let link = ref("Ссылка-приглашение");
</script>

<style scoped>
.info {
  max-width: 360px;
  border-radius: 25px;
  border: 1px solid #8a8a8a;
}
.info__wrapper {
  padding: 35px 35px;
}
.info__title {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.title__subtitle {
  color: #8a8a8a;
  text-align: center;
  font-family: Noto Sans;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  text-transform: uppercase;
}
.title__icon {
}
.info__link {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
}
.link__icon {
}
.link__text {
  color: #e64646;
  font-family: Noto Sans;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
.info__block {
  display: flex;
  flex-direction: column;
  align-content: left;
  padding-top: 20px;
}
.block__title {
  color: #5e5e5e;
  font-family: Noto Sans;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
.block__subtitle {
  color: #8a8a8a;
  font-family: Noto Sans;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
</style>
