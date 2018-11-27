<template>
  <div class="home">
    <section class="hero-section">
      <div class="hero-section__text">
        <h1>WE SHIP OVERNIGHT NATIONWIDE</h1>
        <p>We deliver Tuesday-Friday and offer the ability to schedule ahead</p>
        <btn style="margin-top: 25px;">VIEW MENU</btn>
      </div>
    </section>
    <section class="section-two">
      <h2>YOU BUY IT BY THE BOX</h2>
      <p>Choose 7-8 products of your liking and have it delivered to your door as often as you want. Your pick, every time.</p>
      <div class="section-two__grahics-container">
        <div class="section-two__graphic">
          <div class="section-two__graphic__large-number">01</div>
          <div class="section-two__graphic__text-1">Build Your Box</div>
        </div>
        <div class="section-two__graphic">
          <div class="section-two__graphic__large-number">02</div>
          <div class="section-two__graphic__text-1">Subscribe Or Don't</div>
        </div>
        <div class="section-two__graphic">
          <div class="section-two__graphic__large-number">03</div>
          <div class="section-two__graphic__text-1">Pick a Delivery Day</div>
          <div class="section-two__graphic__text-2">We Ship Overnight.</div>
        </div>     
      </div>
      <btn>SHOP THE MENU</btn>
    </section>
    <carousel></carousel>
    <section class="section-four">
      <div class="horizontal-divider"></div>
      <h2>PICK YOUR PLEASURE</h2>
      <p>Our products are nourishing, satiating and never cut with cheap fillers.</p>
      <div class="drink-image-button-container">
        <image-button
          style="margin: 20px"
          image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265113/ZehnerTest/drinks_lemonade.png">
          VIEW LEMONADES MENU
        </image-button>
        <image-button 
          style="margin: 20px"
          image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265113/ZehnerTest/drinks_milk.png">
          VIEW MILKS MENU
        </image-button>
        <image-button
          style="margin: 20px"
          image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265096/ZehnerTest/drinks_water.png">
          VIEW WATERS MENU
        </image-button>
        <image-button
          style="margin: 20px"
          image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265116/ZehnerTest/drinks_smoothie.png">
          VIEW SMOOTHIES MENU
        </image-button>
      </div>
      <btn style="margin: 20px 0 50px 0">VIEW DRINKS MENU</btn>
    </section>
    <section class="section-five">
      <h1>CLEANSE</h1>
      <div class="horizontal-divider"></div>
      <h2>DRINK YOURSELF CLEAN</h2>
      <p>You like those cupcakes right? Sweet-spot for the whiskey neat? We get it. Time to cleanse.</p>
      <btn>SHOP CLEANSES</btn>
    </section>
    <section class="section-six">
      <h1>LOCATIONS</h1>
      <div class="location-button-container">
        <div class="location-button">
          <image-button
            image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265111/ZehnerTest/locations_platform.png"
            height="203"
            width="271">
            VIEW STORE DETAILS
          </image-button>
          <h4>PLATFORM</h4>
          <p>Monday- Sunday - 7am - 8pm</p>
        </div>
        <div class="location-button">
          <image-button
            image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265101/ZehnerTest/locations_dtla.png"
            height="203"
            width="271">
            VIEW STORE DETAILS
          </image-button>
          <h4>DTLA</h4>
          <p>Monday- Sunday - 7am - 8pm</p>
        </div>
        <div class="location-button">
          <image-button
            image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265101/ZehnerTest/locations_pasadena.png"
            height="203"
            width="271">
            VIEW STORE DETAILS
          </image-button>
          <h4>PASADENA</h4>
          <p>Monday- Sunday - 7:30am - 7pm</p>
          <p>Sunday - 8am - 6pm</p>
        </div>
        <div class="location-button">
          <image-button
            image="https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265111/ZehnerTest/locations_venice.png"
            height="203"
            width="271">
            VIEW STORE DETAILS
          </image-button>
          <h4>VENICE</h4>
          <p>Monday- Sunday - 7am - 8pm</p>
        </div>
      </div>
      <btn>VIEW ALL LOCATIONS</btn>
    </section>
  </div>
</template>

<script>
import Carousel from '@/components/Carousel'
import btn from '@/components/Button'
import ImageButton from '@/components/ImageButton'
export default {
  name: 'home',
  components: {
    Carousel,
    btn,
    ImageButton
  }
}
</script>

<style scoped>
h1 {
  font-size: 3.0em;
}
h2 {
  font-size: 1.8em;
}
h4 {
  font-size: 1.1em;
  font-weight: bold;
  color: #F15B4B;
}
p {
  font-size: 0.9em;
  text-align: center;
}
.section-six {
  min-height: 550px;
  width: 100%;
  padding-bottom: 20px;
  margin-bottom: 50px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.location-button-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 20px;
  height: auto;
}
.location-button {
  margin: 20px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}
.location-button h4 {
  margin-bottom: 0px;
}
.location-button p {
  margin: 10px 0 0 0;
}
.section-five {
  background-image: url("https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265124/ZehnerTest/cleanse_bg.png");
  background-size: cover;
  background-position: 20% 70%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 550px;
  width: 100%;
}
.section-five h1 {
  margin: 0;
}
.section-five h2 {
  margin: 0;
}
.section-five p {
  margin: 30px 0 45px 0;
  width: 400px;
  text-align: center;
  line-height: 1.8em;
}
.horizontal-divider {
  margin-bottom: 10px;
}
.section-two {
  height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #222;
  padding-bottom: 20px;
}
.section-two p {
  text-align: center;
  width: 400px;
}
.section-two__grahics-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 15px;
}
.section-two__graphic {
  width: 150px;
  height: 150px;
  margin: 0 30px;
  position: relative;
}
.section-two__graphic__large-number {
  font-size: 7.0em;
  font-weight: bold;
  position: absolute;
  right: 0;
  color: #F15B4B;
}
.section-two__graphic__text-1 {
  margin-top: 50px;
  width: 130px;
  border-bottom: 1px solid #999;
  line-height: 1.8em;
  font-size: 0.8em;
  font-weight: bold;
  color: #444;
  z-index: 5;
  position: relative;
}
.section-two__graphic__text-2 {
  width: 80px;
  line-height: 1.35em;
  font-size: 0.8em;
  font-weight: bold;
  color: #444;
  z-index: 5;
  position: relative;
}
.drink-image-button-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
}
.section-four {
  min-height: 500px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.section-four h2 {
  margin: 10px;
}
.section-four p {
  width: 370px;
  margin: 10px;
}
.hero-section {
  height: 540px;
  background-image: url("https://res.cloudinary.com/dgr55ydgq/image/upload/v1543265690/ZehnerTest/hero_bg.png");
  background-size: cover;
  background-position: 10% 20%;
  overflow: hidden;
  position: relative;
}
.hero-section__image {
  position: absolute;
  right: 0;
  top: 0;
}
.hero-section__text {
  margin-left: 110px;
  margin-top: 110px;
  width: 580px;
}
.hero-section__text h1 {
  line-height: 1.1em;
}
.hero-section__text p {
  width: 350px;
  line-height: 1.5em;
  text-align: left;
}
</style>

