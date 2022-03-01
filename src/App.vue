<script setup>

import { ref } from "vue";

import SocialIcon from './components/socialIcon.vue'
import FacebookIcon from './components/icons/IconFacebook.vue'
import InstagramIcon from './components/icons/IconInsta.vue'
import IconPlus from './components/icons/IconPlus.vue'

const show = ref(false);
const fadeClass = 'fader'
const bkClass = 'bk'

</script>

<template>
  <div class="heroSection">
    <div class="textConatiner row h-100 ms-1 ms-md-5">
      <div class="col-sm-12 my-auto ms-1 ms-md-5">
        <div v-bind:class="[show ? fadeClass : '', bkClass]">
          <h1>Explore</h1>
          <div class="heroSectionButtons ms-3 ms-md-5" @click="show = !show">
            <IconPlus v-if="!show" />
            <span v-if="!show" class="buttonLabel ms-md-5 ms-3">More Details</span>
          </div>
        </div>

        <Transition name="bounce">
          <div class="heroModal" v-if="show">
            <Transition name="slide-fade" appear>
              <div class="heroModalText">
                <div class="close" @click="show = !show">x</div>
                <h2>Explore</h2>
                <p>
                  Sed ut perspiciatis unde omnis iste natus error sit voluptatem
                  accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
                  quae ab illo inventore veritatis et quasi architecto beatae vitae
                  dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
                  aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
                  eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam
                  est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci
                  velit, sed quia non numquam eius modi tempora incidunt ut labore
                  et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima
                  veniam, quis nostrum exercitationem ullam corporis suscipit
                  laboriosam, nisi ut aliquid ex ea commodi consequatur?
                </p>
                <a class="heroModalButton" href="#" role="button">Read More</a>
              </div>
            </Transition>
          </div>
        </Transition>
      </div>
    </div>
    <div class="colorBar position-absolute"></div>
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
@import "./assets/animations.css";

#app {
  height: 100%;
  width: 100%;
  position: absolute;
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
  left:0;
  bottom: 0;
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
  cursor: pointer;
  position: absolute;
}
.heroSectionButtons .buttonLabel {
  font-size: 2em;
  line-height: 0;
}
.heroModal {
  overflow: hidden;
  position: absolute;
  background: white;
  padding: 4em;
  left: 3rem;
  max-width: 60%;
  z-index: 10;
  bottom: -3rem;
  color: var(--vt-c-text-light-2);
  box-shadow: 1px 1px 20px black;
}

.heroModalText {
  position: relative;
}
.heroModalText h2 {
  font-family: var(--vt-t-heading);
  color: var(--bar-color);
  font-weight: 800;
  font-size: 74px;
  border-radius: 0px;
  box-sizing: content-box;
  margin-bottom: 30px;
}
.heroModalText p {
  background: linear-gradient(#ffffff, #ffffff) 50% 50% / calc(100% - 8px)
      calc(100% - 8px) no-repeat,
    linear-gradient(90deg, #611818 0%, rgba(255, 255, 255, 0) 50%) no-repeat 0 0/100%
      2px;
  border-radius: 0px;
  padding: 30px 0;
  box-sizing: content-box;
  font-family: var(--vt-t-body);
  font-weight: 400;
  font-size: 18px;
  line-height: 36px;
}
.heroModalButton {
  background: rgb(97, 24, 24);
  background: linear-gradient(
    90deg,
    rgba(97, 24, 24, 1) 48%,
    rgba(149, 100, 100, 1) 100%
  );
  padding: 15px 55px;
  border: lightgray 2px solid;
  color: white;
  text-decoration: none;
  text-transform: uppercase;
  font-size: 24px;
  letter-spacing: 2px;
  font-weight: 400;
}
.close {
  right: -30px;
  top: -30px;
  position: absolute;
  font-size: 45px;
  z-index: 11;
  cursor: pointer;
  line-height: 0;
  color: var(--bar-color);
  font-weight: 400;
}

@media (max-width: 640px) {
  body {
  }

  #app {
  }
  .socialContainer {
    position: fixed;
    right: 20px;
    bottom: 20px;
    z-index: 10;
}
.heroSection h1 {
    font-size: 18vw;
    font-family: var(--vt-t-heading);
    font-weight: 800;
    letter-spacing: 3px;
    line-height: 1;
}
.colorBar {
    height: 50%;
    width: 100%;
    bottom: 0;
}
.heroModal{
    position: fixed;
    left: -1.25em;
    bottom: -0;
    max-width: 80%;
    width: 100%;
    margin: 3em;
    padding: 3em 2em;
    margin-top:10px;
}
.heroModal h2{
    font-size: 48px;
    line-height: 18px;
}
.heroModal p{
    font-weight: 400;
    font-size: 16px;
    line-height: 18px;
}
.close {
    right: 0;
    top: 0;
}
.heroModalButton {

    font-size: 18px;

}
}
</style>
