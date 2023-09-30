<template>
  <router-view />
</template>

<script></script>

<style>
@font-face {
  font-weight: 400;
  font-family: "NotoSans";
  src: local("Noto Sans") url("/src/assets/fonts/NotoSans-Black.ttf")
    format("ttf");
}
@font-face {
  font-weight: 700;
  font-family: "NotoSans";
  src: local("Noto Sans") url("/src/assets/fonts/NotoSans-Bold.ttf")
    format("ttf");
}

*,
*::before,
*::after {
  padding: 0;
  margin: 0;
  border: 0;
  box-sizing: border-box;
}
a {
  text-decoration: none;
}
ul,
ol,
li {
  list-style: none;
}
img {
  vertical-align: top;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 400;
  font-size: 30px;
  color: #313131;
}
html,
body {
  height: 100%;
  line-height: 1;
  font-size: 20px;
  background: #171717;
}
</style>
