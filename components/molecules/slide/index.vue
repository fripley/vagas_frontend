<template>
  <div class="slide-container">
    <span :class="['tag', verifyDiscount(percent)]">{{ `$ ${parseInt(Math.abs(percent))}` }}</span>
    <figure class="image-wrapper">
      <img :src="image" :alt="title" class="image-slide">
    </figure>
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
  },
  methods: {
    verifyDiscount (n) {
      const res = Math.sign(n)
      switch (res) {
        case 1:
          return 'positive'
        case -1:
          return 'negative'
        default:
          return 'neutral'
      }
    }
  }
}
</script>

<style lang="scss">
.slide-container {
  border: 2px solid #9d9d9d;
  border-radius: 8px;
  text-align: center;
  max-width: 380px;
  margin: 0 auto;
  padding: 16px 48px 60px;
  width: 100%;
}
@media screen and (min-width: 1024px) {
  .slide-container {
    cursor: pointer;
    transition: box-shadow .3s;
    &:hover {
      box-shadow: -2px 2px 12px rgba(0, 0, 0, .3);
    }
  }
}
.title-slide {
  margin-top: 16px;
  text-overflow: ellipsis;
  max-height: 42px;
  white-space: nowrap;
  overflow-wrap: break-word;
  overflow: hidden;
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
.image-wrapper {
  height: 275px;
  overflow: hidden;
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
.tag {
  position: absolute;
  top: 24px;
  left: 0;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
  padding: 16px;
  color: #fff;
  display: flex;
  flex-direction: row;
  align-items: center;
}
@media screen and (min-width: 1024px) {
  .tag {
    padding: 8px 12px;
    font-size: 14px;
  }
}
.tag:before {
  content: '';
  display: inline-block;
  width: 16px;
  height: 16px;
  background: url(~assets/triangle-copy.png) 0 0 no-repeat;
  background-size: contain;
  margin-right: 8px;
}
.tag.negative {
  background-color: #c1180f;
}
.tag.positive {
  background-color: #13bc4a;
}
.tag.negative:before,
.tag.neutral:before {
  transform: rotate(180deg);
}
.tag.neutral {
  background-color: #848484;
}
</style>
