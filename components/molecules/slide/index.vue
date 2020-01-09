<template>
  <div class="slide-container">
    <img :src="image" :alt="title" class="image-slide">
    <Title :label="title" class="tertiary title-slide" />
    <span class="business-slide">
      Vendido por <strong>{{ business }}</strong>
    </span>
    <h5 class="price-slide">
      {{ `R$ ${price.toFixed(2).replace(/[.]/g, ',')}` }}
    </h5>
  </div>
</template>

<script>
import Title from '~/components/atoms/title'

export default {
  components: {
    Title
  },
  props: {
    image: {
      type: String,
      default: ''
    },
    business: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    percent: {
      type: Number,
      default: 0
    },
    price: {
      type: Number,
      default: 0
    }
  }
}
</script>

<style>
.slide-container {
  border: 2px solid #9d9d9d;
  border-radius: 8px;
  text-align: center;
  max-width: 380px;
  margin: 0 auto;
  padding: 0 0 60px;
}
.title-slide {
  margin-top: 16px;
}
.business-slide {
  font-size: 20px;
  margin: 36px 0 16px;
  display: block;
}
.business-slide strong {
  color: #3aacd1;
  font-weight: 600;
}
.image-slide {
  width: 100%;
  max-width: 350px;
  height: auto;
  max-height: 300px;
  align-self: center;
  display: block;
  margin: 0 auto;
}
.price-slide {
  color: #5555d9;
  font-weight: 600;
  font-size: 28px;
}
</style>
