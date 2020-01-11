<template>
  <div class="container">
    <Header />
    <div class="wrapper">
      <Hero />
    </div>
    <div class="wrapper pillar-section">
      <Pillars />
    </div>
    <div class="wrapper">
      <VideoDisclosure class="mb-136" />
      <Title label="Marcas do app em destaque" class="mb-32 align-center" />
      <div class="inner-wrapper">
        <Spotlight :business="businessPlaceholder" />
        <Resume />
      </div>
      <AppAdd is-reverse />
    </div>
    <Slider class="mb-136" />
    <Footer />
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
import Footer from '~/components/organisms/footer'
import Title from '~/components/atoms/title'

import Business from '~/json/lojas.json'
import Products from '~/json/produtos.json'

export default {
  components: {
    Title,
    Header,
    Hero,
    Pillars,
    VideoDisclosure,
    Spotlight,
    Resume,
    Slider,
    Footer,
    AppAdd
  },
  data () {
    return {
      business: [],
      products: [],
      businessPlaceholder: [
        { name: '', bgColor: '#1da1f2' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#ff4600' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#9746d5' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fff' },
        { name: '', bgColor: '#fedb00' }
      ]
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
@media screen and (min-width: 769px){
  .wrapper {
    max-width: 1024px;
    align-self: center;
  }
}
.container .wrapper:first-child {
  margin-bottom: 88px
}
.pillar-section {
  background-color: #f7ffdc;
  padding: 48px 16px;
  max-width: 100%;
}
@media screen and (min-width: 1024px) {
  .inner-wrapper {
    display: grid;
    grid-template-columns: 40% 60%;
    align-items: center;
    grid-column-gap: 16px;
  }
}
</style>
