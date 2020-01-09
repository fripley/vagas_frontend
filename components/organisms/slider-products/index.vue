<template>
  <div class="slider-container">
    <HeaderSlider />
    <div v-swiper:mySwiper="swiperOption" class="swiper-container">
      <div class="swiper-wrapper">
        <div v-for="(item, key) in Products" :key="key" class="swiper-slide">
          <ProductSlider
            :image="item.image"
            :title="item.title"
            :percent="item.percentage"
            :price="item.price"
            :business="filterBusiness(item.storeid)"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderSlider from '~/components/molecules/header-slider'
import ProductSlider from '~/components/molecules/slide'
import Business from '~/json/lojas.json'
import Products from '~/json/produtos.json'

export default {
  components: {
    HeaderSlider,
    ProductSlider
  },
  data () {
    return {
      Business,
      Products,
      swiperOption: {
        loop: false,
        slidesPerView: 'auto',
        centeredSlides: true,
        spaceBetween: 30
      }
    }
  },
  methods: {
    filterBusiness (idstore) {
      for (let i = 0; i < this.Business.length; i++) {
        if (this.Business[i].id === idstore) {
          return this.Business[i].name
        }
      }
    }
  }
}
</script>

<style>
.slider-container {
  align-self: center;
  max-width: calc(100vw - 24px);
  justify-content: center;
}
.my-swiper {
  height: 300px;
  width: 100%;
}
.swiper-container {
  margin-top: 24px;
}
.swiper-wrapper {
  right: 40px;
}
@media screen and (max-width: 500px) {
  .swiper-wrapper {
    right: 0;
  }
}
.swiper-slide {
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  width: auto;
  max-width: calc(100% - 32px);
}
.swiper-pagination-bullet {
  background-color: red;
}
</style>
