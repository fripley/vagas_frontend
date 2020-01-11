<template>
  <div id="app-disclosure" :class="['app-disclosure-container', isReverse && 'reverse']">
    <article :class="['text-block', isReverse && 'mt-48']">
      <BoxText
        :class="[!isPhone && 'align-center']"
        :subtitle="!isPhone"
        title-label="Título da página"
        text-label="Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic molestias blanditiis magni praesentium repellat."
      />
      <AppLinkDownload v-show="isPhone" />
    </article>
    <div :class="[isPhone ? 'image-block' : 'video-block']">
      <img v-if="isPhone" :src="image" alt="phone">
      <iframe v-else src="https://www.youtube.com/embed/sCxQFlkgzrw" />
    </div>
  </div>
</template>

<script>
import BoxText from '~/components/molecules/box-title-text'
import AppLinkDownload from '~/components/molecules/app-link-download'

const phone1 = require('~/assets/group-9.png')
const phone2 = require('~/assets/group-11.png')

export default {
  components: {
    BoxText,
    AppLinkDownload
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
  },
  data () {
    return {
      image: this.$props.isReverse ? phone2 : phone1
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
  margin: 98px auto;
}
@media screen and (min-width: 1024px) {
  .app-disclosure-container {
    max-width: 100%;
    flex-direction: row;
    min-height: 500px;
    display: grid;
    margin-top: 88px;
    grid-template-columns: 50% 50%;
  }
  .app-disclosure-container.reverse .app-controller {
    margin-top: 64px;
  }
  .app-disclosure-container.reverse .image-block{
    grid-column: 1;
    grid-row: 1;
    justify-self: flex-start;
  }
}
.app-disclosure-container.reverse {
  flex-direction: column-reverse;
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
@media screen and (min-width: 1024px) {
  .image-block {
    justify-self: flex-end;
  }
}
.video-block,
.video-block  iframe{
  width: 100%;
  height: 100%;
}
.image-block > img {
  height: auto;
  width: 100%;
}
/* @media screen and (min-width: 1024px) {
  .video-block > iframe {
    min-width: 500px;
    width: 100%;
  }
  .video-block {
    max-width: 100%;
    height: 100%;
  }
} */
</style>
