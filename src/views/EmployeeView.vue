<template>
  <div class="wrapper">
    <header class="header">
      <div class="header__wrapper">
        <div v-if="role === 'employee'" class="header__greetings">
          <img
            src="../assets/img/dashboard/header_greet.png"
            alt="hello"
            class="greetings__icon"
          />
          <h1 class="greetings__title">Привет, {{ name }}!</h1>
          <p class="greetings__subtitle">#{{ rating }} В РЕЙТИНГЕ</p>
        </div>
        <div v-else-if="role === 'company'" class="header__greetings">
          <img
            src="../assets/img/dashboard/header_greet.png"
            alt="hello"
            class="greetings__icon"
          />
          <h1 class="greetings__title">{{ name }}</h1>
          <p class="greetings__subtitle">#{{ rating }} СОТРУДНИКОВ</p>
        </div>
        <div v-else-if="role === 'fond'" class="header__greetings">
          <img
            src="../assets/img/dashboard/header_greet.png"
            alt="hello"
            class="greetings__icon"
          />
          <h1 class="greetings__title">{{ name }}</h1>
          <p class="greetings__subtitle">хз че</p>
        </div>
        <div class="header__btn">
          <img
            src="../assets/img/dashboard/exit.svg"
            alt="exit"
            class="btn__icon"
          />
          <a href="http://localhost:8080/" class="btn__text">Выход</a>
        </div>
      </div>
    </header>

    <div class="dashboard">
      <div class="dashboard__wrapper">
        <Info></Info>
        <div class="dashboard__activities">
          <div class="activities__wrapper">
            <div class="activities__header">
              <h2 class="header__title">ФИЗИЧЕСКАЯ АКТИВНОСТЬ</h2>
            </div>
            <div class="activities__blocks">
              <div class="blocks__block">
                <div class="block__wrapper">
                  <p class="block__title">1280</p>
                  <p class="block__subtitle">рублей вы пожертвовали</p>
                </div>
              </div>
              <div class="blocks__block">
                <div class="block__wrapper">
                  <p class="block__title">1280</p>
                  <p class="block__subtitle">рублей вы пожертвовали</p>
                </div>
              </div>
              <div class="blocks__block">
                <div class="block__wrapper">
                  <p class="block__title">1280</p>
                  <p class="block__subtitle">рублей вы пожертвовали</p>
                </div>
              </div>
              <div class="blocks__block">
                <div class="block__wrapper">
                  <p class="block__title">1280</p>
                  <p class="block__subtitle">рублей вы пожертвовали</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="dashboard__achivments">
          <div class="achivments__wrapper">
            <div class="achivments__header">
              <p class="header__title">ДОСТИЖЕНИЯ</p>
            </div>
            <div class="achivments__blocks">
              <img
                v-for="medal in medals"
                :key="medal.alt"
                src="../assets/img/dashboard/medal.png"
                alt=""
                class="achive__icon"
              />
            </div>
            <div class="achivments__more">
              <img
                src="../assets/img/dashboard/more.svg"
                alt="more"
                class="more__icon"
              />
              <p class="more__text">показать больше</p>
            </div>
          </div>
        </div>
        <!-- <div class="dashboard__table">
          <Table></Table>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script setup>
import Info from "@/components/Info.vue";
import Table from "@/components/Table.vue";
import { ref } from "vue";

let medals = [
  {
    src: "../assets/img/dashboard/medal.png",
    alt: "medal",
  },
  {
    src: "../assets/img/dashboard/medal.png",
    alt: "medal",
  },
  {
    src: "../assets/img/dashboard/medal.png",
    alt: "medal",
  },
  {
    src: "../assets/img/dashboard/medal.png",
    alt: "medal",
  },
  {
    src: "../assets/img/dashboard/medal.png",
    alt: "medal",
  },
  {
    src: "../assets/img/dashboard/medal.png",
    alt: "medal",
  },
];
let role = ref("employee");
let name = ref("Ivan Ivanovich");
let rating = ref(6);
</script>

<style scoped>
body {
  background: #171717;
}
.wrapper {
  max-width: 1500px;

  display: flex;
  flex-direction: column;
  margin: 0px auto;
}
.header {
  padding-top: 50px;
}
.header__wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.header__greetings {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.greetings__icon {
  max-width: 44px;
  max-height: 44px;
}
.greetings__title {
  color: var(--Text-1, #fafaf9);
  text-align: center;
  font-family: Noto Sans;
  font-size: 35px;
  font-style: normal;
  font-weight: 900;
  line-height: 105px; /* 300% */
  padding: 0px 30px;
}
.greetings__subtitle {
  color: #7a29dc;
  font-family: Noto Sans;
  font-size: 20px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  text-transform: uppercase;
}
.header__btn {
  display: flex;
  flex-direction: row;
}
.btn__icon {
  padding: 0px 8px;
}
.btn__text {
  color: #e64646;
  font-family: Noto Sans;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}
.dashboard {
  margin-top: 100px;
}
.dashboard__wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.dashboard__activities {
  border-radius: 25px;
  background: #fafaf9;
}
.activities__wrapper {
  padding: 30px;
}
.activities__header {
  margin-bottom: 35px;
}
.header__title {
  color: #787a86;
  font-family: Noto Sans;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  text-transform: uppercase;
}
.activities__blocks {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
}
.blocks__block {
  border-radius: 15px;
  background: #e6e6e6;
  max-width: 160px;
  text-align: center;
}
.blocks__block:not(:last-child) {
  margin-right: 10px;
}
.block__wrapper {
  padding: 30px;
}
.block__title {
  color: #e64646;
  font-family: Noto Sans;
  font-size: 35px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
}
.block__subtitle {
  color: #4f4f4f;
  text-align: center;
  font-family: Noto Sans;
  font-size: 12px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}
.dashboard__achivments {
  border-radius: 25px;
  background: #323443;
  max-width: 350px;
}
.achivments__wrapper {
  padding: 30px;
}
.achivments__header {
}
.achivments__blocks {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin-top: 25px;
  justify-content: space-around;
}
.blocks__achive {
}
.achive__icon {
  margin-top: 10px;
}
.achivments__more {
  display: flex;
  justify-content: center;
  margin-top: 25px;
}
.more__icon {
  padding-top: 3px;
  padding-right: 5px;
}
.more__text {
  color: rgba(120, 122, 134, 0.57);
  font-family: Noto Sans;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
</style>
