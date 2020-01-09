<template>
  <div id="slider" class="slider-container">
    <HeaderSlider />
    <!-- <div v-swipe:mySwiper="swiperOption"> -->
      <div class="swiper-wrapper">
        <template v-for="item in products" class="swiper-slide">
          <ProductSlider
            :key="item.id"
            :image="item.image"
            :title="item.title"
            :percent="item.percentage"
            :price="item.price"
            :business="filterBusiness(item.storeid)"
          />
        </template>
      </div>
    <!-- </div> -->
  </div>
</template>

<script>
// import mySwiper from 'vue-awesome-swiper'
import HeaderSlider from '~/components/molecules/header-slider'
import ProductSlider from '~/components/molecules/slide'
import Business from '~/json/lojas.json'
import Products from '~/json/produtos.json'

export default {
  components: {
    HeaderSlider,
    ProductSlider
  },
  mounted () {
    console.log(this.mySwiper)
  },
  data () {
    return {
      products: Products,
      business: Business,
      mySwiper,
      swiperOption: {
        loop: true,
        slidesPerView: 'auto',
        centeredSlides: true,
        spaceBetween: 30,
        pagination: {
          el: '.swiper-pagination',
          dynamicBullets: true
        },
        on: {
          slideChange () {
            console.log('onSlideChangeEnd', this)
          },
          tap () {
            console.log('onTap', this)
          }
        }
      }
    }
  },
  methods: {
    filterBusiness (idstore) {
      for (let i = 0; i < this.business.length; i++) {
        if (this.business[i].id === idstore) {
          return this.business[i].name
        }
      }
    }
  }
}
</script>

<style>
.slider-container {
  align-self: center;
  max-width: 470px;
  justify-content: center;
}
</style>
