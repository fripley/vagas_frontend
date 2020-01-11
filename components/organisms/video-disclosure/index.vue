<template>
  <section id="video-disclosure" class="video-disclosure-wrapper">
    <AppDisclosure />
  </section>
</template>

<script>
import AppDisclosure from '~/components/molecules/app-disclosure'

export default {
  components: {
    AppDisclosure
  }
}
</script>

<style lang="scss">
@media screen and (min-width: 1024px) {
  .video-disclosure-wrapper .app-disclosure-container {
    grid-template-columns: none;
    grid-template-rows: 175px 500px;
  }
  .video-disclosure-wrapper {
    .app-disclosure-container {
      .text-box {
        margin: 0 auto;
        max-width: 700px;
        h1 {
          text-align: center;
        }
      }
      .paragraph-container  {
        text-align: center;
      }
    }
  }
}
</style>
