<template>
  <div class="carousel-item">
    <h1>DRINKS</h1>
    <div class="horizontal-divider"></div>
    <h2>JUICES</h2>
    <p>Our juices are individually crafted to flush, detoxify, hydrate, and strengthen the body.</p>
    <btn>VIEW JUICE MENU</btn>
  </div>
</template>

<script>
import btn from '@/components/Button.vue'
export default {
  components: {
    btn
  }
}
</script>

<style scoped>
.carousel-item {
  background-image: url("https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265117/ZehnerTest/carousel_1.png");
  background-size: cover;
  background-position: 20% 20%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  color: #222;
  position: absolute;
  top: 0;
}
.carousel-item h1 {
  font-size: 3.2em;
  margin: 0;
}
.carousel-item h2 {
  font-size: 1.8em;
  margin: 0;
}
.carousel-item p {
  margin: 30px 0 45px 0;
  width: 400px;
  text-align: center;
}
</style>
