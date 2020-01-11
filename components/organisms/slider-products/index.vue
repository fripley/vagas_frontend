<template>
  <div class="slider-container">
    <HeaderSlider />
    <div v-swiper:mySwiper="$device.isDesktop ? swiperOptionB : swiperOptionA" class="swiper-container">
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
    <a href="javascript:;" class="swiper-button-next" @click="() => this.mySwiper.slideNext()">
      <img src="~assets/seta.png" alt="">
    </a>
    <a href="javascript:;" class="swiper-button-prev" @click="() => this.mySwiper.slidePrev()">
      <img src="~assets/seta.png" alt="">
    </a>
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
      swiperOptionA: {
        loop: false,
        slidesPerView: 'auto',
        centeredSlides: true,
        spaceBetween: 30
      },
      swiperOptionB: {
        loop: false,
        slidesPerView: 4,
        centeredSlides: false,
        spaceBetween: 16,
        slidesPerGroup: 4
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

<style lang="scss">
.slider-container {
  align-self: center;
  max-width: calc(100vw - 24px);
  justify-content: center;
}
.swiper-button-next,
.swiper-button-prev {
  display: none;
}
@media screen and (min-width: 1024px) {
  .slider-container {
    position: relative;
  }
  .swiper-container {
    .slide-container {
      max-width: 300px;
      padding: 16px 24px 24px;
      .title-slide {
        font-size: 18px;
      }
      .business-slide {
        font-size: 14px;
      }
      .price-slide {
        font-size: 18px;
      }
      .image-slide {
        max-width: 280px;
      }
      .image-wrapper {
        height: 245px;
      }
    }
  }
  .swiper-button-prev,
  .swiper-button-next {
    position: absolute;
    display: block;
    top: 60%;
    transform: translateY(-50%);
    width: 45px;
    height: 45px;
    background-image: none;
    img {
      display: block;
      width: 100%;
    }
  }
  .swiper-button-next {
    right: -55px;
  }
  .swiper-button-prev {
    left: -55px;
    img {
      transform: rotate(-180deg);
    }
  }
  .swiper-button-disabled {
    display: none;
  }
  .swiper-container {
    overflow: hidden;
    max-width: 1024px;
  }
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
@media screen and (min-width: 1024px) {
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
