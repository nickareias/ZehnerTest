<template>
  <div class="carousel-container">
    <transition-group mode="out-in" name="carousel-item">
      <component 
        v-for="(component, index) in carouselItems"
        :is="component" 
        :key="'carousel-item' + index"
        v-if="index === carouselIndex"
      ></component>
    </transition-group>
    <div class="carousel-button-container">
      <button 
        class="carousel-button" 
        @click="selectSlide(index)" 
        v-for="(component, index) in carouselItems"
        :key="'carousel-item' + index"
        :class="{'carousel-button--selected': index === carouselIndex}"
      ></button>
    </div>
  </div>
</template>

<script>
import CarouselItemOne from '@/components/CarouselItemOne'
export default {
  data() {
    return {
      carouselIndex: 0,
      slideTimer: 0,
      slideDuration: 1500
    }
  },
  mounted() {
    setInterval(this.slideCountdown, 1)
  },
  computed: {
    getCarouselItem() {
      return this.carouselItems[this.carouselIndex]
    },
    carouselItems() {
      return [CarouselItemOne, CarouselItemOne, CarouselItemOne]
    }
  },
  methods: {
    slideCountdown() {
      if (this.slideTimer >= this.slideDuration) {
        this.carouselIndex = (this.carouselIndex + 1) % this.carouselItems.length
        this.slideTimer = 0
      } else {
        this.slideTimer += 1
      }
    },
    selectSlide(index) {
      this.carouselIndex = index
      this.slideTimer = 0
    }
  }
}
</script>

<style scoped>
.carousel-button-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
  z-index: 100;
  position: absolute;
  bottom: 0;
  left: 50%;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%)
}
.carousel-button {
  width: 15px;
  height: 15px;
  border-radius: 50%;
  border: none;
  margin: 10px;
  background-color: white;
  cursor: pointer;
}
.carousel-button--selected {
  background-color: #F15B4B;
}
.carousel-container {
  width: 100%;
  height: 519px;
  position: relative;
}
.carousel-item-enter-active, .carousel-item-leave-active {
  transition: all 1s;
}
.carousel-item-enter /* .list-leave-active below version 2.1.8 */ {
  transform: translateX(100vw);
}
.carousel-item-leave-to {
  transform: translateX(-100vw);
}
</style>
