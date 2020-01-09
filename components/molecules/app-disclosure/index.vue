<template>
  <div id="app-disclosure" :class="['app-disclosure-container', isReverse && 'reverse']">
    <article :class="['text-block', isReverse && 'mt-48']">
      <BoxText
        :class="[!isPhone && 'align-center']"
        :subtitle="!isPhone"
        title-label="Título da página"
        text-label="Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic molestias blanditiis magni praesentium repellat."
      />
      <div v-show="isPhone" class="app-controller">
        <a href="javascript:;" title="google play">
          <img src="~/assets/google-play.png" alt="google play">
        </a>
        <a href="javascript:;" title="app store">
          <img src="~/assets/download-on-the-app-store-badge-ptbr-rgb-blk-092917.png" alt="app store">
        </a>
      </div>
    </article>
    <div :class="[isPhone ? 'image-block' : 'video-block']">
      <img v-if="isPhone" src="~/assets/group-9.png" alt="phone">
      <!-- <iframe v-else src="https://www.youtube.com/embed/sCxQFlkgzrw" height="300" /> -->
    </div>
  </div>
</template>

<script>
import BoxText from '~/components/molecules/box-title-text'

export default {
  components: {
    BoxText
  },
  props: {
    isPhone: {
      type: Boolean,
      default: false
    },
    isReverse: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style>
.app-disclosure-container {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 48px auto;
}
.app-disclosure-container.reverse {
  flex-direction: column-reverse;
}
.app-controller {
  display: flex;
  justify-content: space-between;
}
@media screen and (max-width: 460px) {
  .app-controller {
    flex-wrap: wrap;
    justify-content: center;
  }
  .app-controller > a:first-child {
    margin-bottom: 16px;
  }
}
.text-block > p {
  font-size: 18px;
}
.text-block img {
  width: 100%;
}
.image-block {
  margin-top: 32px;
  max-width: 420px;
}
.video-block {
  max-width: 500px;
}
.image-block > img {
  height: auto;
  width: 100%;
}
.video-block > iframe {
  min-width: 500px;
}
</style>
