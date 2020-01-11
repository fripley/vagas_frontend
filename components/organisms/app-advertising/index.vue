<template>
  <section id="app-advertising">
    <AppDisclosure is-phone is-reverse />
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
  #app-advertising {
    .text-box {
      max-width: 100%;
    }
  }
}
</style>
