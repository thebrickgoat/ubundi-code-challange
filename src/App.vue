<script setup>

import SocialIcon from './components/socialIcon.vue'
import FacebookIcon from './components/icons/IconFacebook.vue'
import InstagramIcon from './components/icons/IconInsta.vue'
import IconPlus from './components/icons/IconPlus.vue'


</script>

<template>
  <div class="heroSection">
    <div class="textConatiner row h-100 ms-5">
      <div class="col-sm-12 my-auto ms-5">
        <h1>Explore</h1>
        <div class="heroSectionButtons ms-5">
          <IconPlus />
          <span class="buttonLabel ms-3">More Details</span>
        </div>
      </div>
    </div>
    <div class="colorBar position-absolute top-0 start-0"></div>
  </div>
  <section class="socialContainer">
    <SocialIcon buttonlink="facebook.com">
      <template #icon>
        <FacebookIcon />
      </template>
    </SocialIcon>
    <SocialIcon buttonlink="instagram.com">
      <template #icon>
        <InstagramIcon />
      </template>
    </SocialIcon>
  </section>
</template>

<style>
@import "./assets/base.css";

#app {
  height: 100%;
  width: 100%;
  position: absolute;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}
.heroSection {
  width: 100%;
  height: 100%;
  overflow: hidden;
  background: url("./assets/Coding-Challenge-Image.png");
  background-size: cover;
}
.heroSection h1 {
  font-size: 18vw;
  font-family: var(--vt-t-heading);
  font-weight: 800;
  letter-spacing: 10px;
  line-height: 1;
}

.colorBar {
  background-color: var(--bar-color);
  height: 100%;
  width: 30%;
  z-index: 0;
}
.textConatiner {
  z-index: 1;
}
.socialContainer {
  position: fixed;
  right: 60px;
  bottom: 40px;
  z-index: 10;
}
.heroSectionButtons {
  margin-top: 0;
  display: flex;
  align-items: center;
}
.heroSectionButtons .buttonLabel
    {font-size: 2em;
    line-height: 0;}
@media (min-width: 1024px) {
  body {
  }

  #app {
  }
}
</style>
