<template>
  <div class="container">
    <div class="wrapper">
      <Header />
      <Hero />
    </div>
    <div class="wrapper pillar-section">
      <Pillars />
    </div>
    <div class="wrapper">
      <VideoDisclosure class="mb-136" />
      <Spotlight :business="business" />
      <Resume />
      <AppAdd />
    </div>
    <Slider />
  </div>
</template>

<script>
import Header from '~/components/organisms/header'
import Hero from '~/components/organisms/hero'
import Pillars from '~/components/organisms/pillars'
import Spotlight from '~/components/organisms/spotlight'
import VideoDisclosure from '~/components/organisms/video-disclosure'
import Resume from '~/components/organisms/resume'
import AppAdd from '~/components/organisms/app-advertising'
import Slider from '~/components/organisms/slider-products'
import Business from '~/json/lojas.json'
import Products from '~/json/produtos.json'

export default {
  components: {
    Header,
    Hero,
    Pillars,
    VideoDisclosure,
    Spotlight,
    Resume,
    Slider,
    AppAdd
  },
  data () {
    return {
      business: [],
      products: []
    }
  },
  created () {
    this.getData()
  },
  methods: {
    getData () {
    // async getData () {
      // const business = await this.$axios.get('https://api.myjson.com/bins/nher8')
      // const products = await this.$axios.get('https://api.myjson.com/bins/1gnnec')
      // this.business = business.data
      // this.products = products.data
      this.products = Products
      this.business = Business
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.wrapper {
  width: 100%;
  padding: 0 32px;
}
.container .wrapper:first-child {
  margin-bottom: 88px
}
.pillar-section {
  background-color: #f7ffdc;
  padding: 48px 16px;
}
</style>
