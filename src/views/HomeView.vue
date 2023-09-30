<template>
  <div class="main">
    <div class="main__wrapper">
      <div class="main__text">
        <img src="" alt="" class="text__icon" />
        <div class="text__title">
          <p>превращай шаги в добро</p>
        </div>
        <div class="text__subtitle">
          <p>
            Каждый шаг вперед – это шанс сделать мир лучше. Прокачайте свою
            физическую активность и помогите тем, кто нуждается!
          </p>
        </div>
        <a class="text__btn" href="http://localhost:8080/dashboard"
          >Присоединиться</a
        >
        <div class="text__download">
          <img src="../assets/img/main/qr.png" alt="" class="download__icon" />
          <p class="download__text">Сканируй QR код и скачивай приложение</p>
        </div>
      </div>
      <Login ref="modal" :show-modal="modal"></Login>
    </div>
  </div>
</template>

<script setup>
import Login from "@/components/Login.vue";
import { ref } from "vue";

let modal = ref(false);

function showModal() {
  modal = true;
  console.log(modal);
}
</script>

<style scoped>
.main {
  height: 100%;
  display: flex;
  flex-direction: column;
  background: url(../assets/img/main/bg.png);
  align-items: center;
  font-family: Noto Sans;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.main__wrapper {
  max-width: 1500px;
  overflow: hidden;
  background-image: url(../assets/img/main/man.png);
  background-repeat: no-repeat;
  background-position: bottom 15px right 100px;
}
.main__text {
  padding-top: 88px;
  text-align: left;
}
.text__icon {
}
.text__title {
  color: var(--Text-1, #fafaf9);
  font-family: Noto Sans;
  font-size: 120px;
  font-style: normal;
  font-weight: 800;
  line-height: 135px; /* 112.5% */
  text-transform: uppercase;
  max-width: 1250px;
}
.text__subtitle {
  color: #8a8a8a;
  font-family: Noto Sans;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  max-width: 570px;
  padding: 60px 0px;
}
.text__btn {
  border-radius: 10px;
  background: #e6533c;
  display: inline-flex;
  padding: 24px 25px;
  align-items: flex-start;
  gap: 10px;
  color: #fff;
  transition: 0.3s all ease;
}
.text__btn:hover {
  transition: 0.3s all ease;
  background: #fff;
  color: #e6533c;
  cursor: pointer;
}
.text__download {
  border-radius: 19px;
  background: #303030;
  display: flex;
  flex-direction: row;
  max-width: 400px;
  align-items: center;
  margin: 100px 0px;
}
.download__icon {
  padding: 15px 25px;
}
.download__text {
  color: #fff;
  font-family: Noto Sans;
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
.main__modal {
  position: absolute;
  top: 0;
  left: 0;
  min-height: 100%;
  width: 100%;
  background: rgba(0, 0, 0, 0.39);
}
</style>
