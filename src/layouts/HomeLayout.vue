<template>
  <div>
    <div class="header" @click="navBarSelect(null)">
      <transition name="slide-up">
        <div class="alert-bar" v-if="alertOpen">
          <p>{{getAlertText}}&nbsp;<a class="alert-bar__cta-button">{{getAlertButtonText}}</a></p>
          <div class="alert-bar__close-button__container">
            <button 
              class="alert-bar__close-button" 
              @click="alertOpen=false"><img src="@/assets/close.svg" height="12px" width="12px"/></button>
          </div>
        </div>
      </transition>
      <div class="nav-bar">
        <div class="nav-bar__login">
          <button class="nav-bar__button--small nav-bar__button">Log In</button>
        </div>
        <div class="nav-bar__group1">
          <button 
            @click.stop="navBarSelect('shop')"
            :class="{'nav-bar__button': true, 'nav-bar__button--selected': isNavButtonSelected('shop')}"
          >
            SHOP
          </button>
          <button 
            @click.stop="navBarSelect('cleanses')"
            :class="{'nav-bar__button': true, 'nav-bar__button--selected': isNavButtonSelected('cleanses')}"
          >
            CLEANSES
          </button>
          <button 
            @click.stop="navBarSelect('build')"
            :class="{'nav-bar__button': true, 'nav-bar__button--selected': isNavButtonSelected('build')}"
          >
            BUILD A BOX
          </button>
        </div>
        <div class="nav-bar__logo">
          <img src="@/assets/logo.png">
          <div class="vertical-divider"></div>
          <div class="nav-bar__title">JUICE</div>
          <div class="vertical-divider"></div>
          <div class="nav-bar__subtitle">SERVED HERE</div>
        </div>
        <div class="nav-bar__group2">
          <button class="nav-bar__button">THE UNCONVENTIONAL</button>
          <button class="nav-bar__button">WHO WE ARE</button>
        </div>
        <div class="nav-bar__cart">
          <img src="@/assets/box_hover.svg" height="15px" width="15px"/>
          &nbsp;
          <div class="nav-bar__cart__amount">(2)</div>
        </div>
      </div>
    </div>
    <transition name="menu-slide">
      <div class="nav-bar__menu" v-if="menuOpen">
        <div class="nav-bar__menu__column">
          <h1>DRINKS</h1>
          <button class="nav-bar__menu__button">All</button>
          <button class="nav-bar__menu__button">Juices</button>
          <button class="nav-bar__menu__button">Smoothies</button>
          <button class="nav-bar__menu__button">Cleanse Packs</button>
          <button class="nav-bar__menu__button">Shots</button>
          <button class="nav-bar__menu__button">Coffee</button>
          <button class="nav-bar__menu__button">Water</button>
        </div>
        <div class="nav-bar__menu__column">
          <h1>GOODS</h1>
          <button class="nav-bar__menu__button">All</button>
          <button class="nav-bar__menu__button">Teas</button>
          <button class="nav-bar__menu__button">Coffees</button>
          <button class="nav-bar__menu__button">Vitals</button>
          <button class="nav-bar__menu__button">Snacks</button>
        </div>
        <div class="nav-bar__menu__column">
          <h1>BOXES</h1>
          <button class="nav-bar__menu__button">All</button>
          <button class="nav-bar__menu__button">Favorites Box</button>
          <button class="nav-bar__menu__button">Sweet Cream Box</button>
          <button class="nav-bar__menu__button">Detox Box</button>
          <button class="nav-bar__menu__button">Greens Box</button>
        </div>
        <div class="nav-bar__menu__column">
          <h1>CLEANSES</h1>
          <button class="nav-bar__menu__button">All</button>
          <button class="nav-bar__menu__button">Soft Cleanse</button>
          <button class="nav-bar__menu__button">Semi Cleanse</button>
          <button class="nav-bar__menu__button">Hard Cleanse</button>
        </div>
        <img src="@/assets/menu_bg.png"/>
      </div>
    </transition>
    <div @click="navBarSelect(null)">
      <slot></slot>
    </div>
    <div class="footer">
      <div class="footer__email-input">
        <h3>LET'S BE FRIENDS WITH BENEFITS</h3>
        <div class="footer__email-input__field-and-button-container">
          <input placeholder="Email Address" type="email"></input>
          <btn small>OK!</btn>
        </div>
      </div>
      <div class="footer__column">
        <h5>COMPANY</h5>
        <div class="footer-button">Find Stores</div>
        <div class="footer-button">Our Story</div>
        <div class="footer-button">Our Juice</div>
        <div class="footer-button">Our Farmers</div>
        <div class="footer-button">Our Commitment</div>
        <div class="footer-button">Careers</div>
      </div>
      <div class="footer__column">
        <h5>HELP</h5>
        <div class="footer-button">FAQ</div>
        <div class="footer-button">Shipping</div>
        <div class="footer-button">Return Policy</div>
        <div class="footer-button">Gift Cards</div>
        <div class="footer-button">Contact Us</div>
        <div class="footer-button">Legal</div>
      </div>
      <div class="footer__column">
        <h5>Social</h5>
        <div class="footer-button">Instagram</div>
        <div class="footer-button">Facebook</div>
        <div class="footer-button">Twitter</div>
      </div>
    </div>
    <div class="footer__bottom">
      <div>©2016. Juice Served Here. NEVER CONVENTIONAL. All Rights Reserved</div>
      <div class="footer__bottom__button-container">
        <div>Privacy Policy</div>
        <div>Terms & Conditions</div>
      </div>
    </div>
  </div>
</template>

<script>
import btn from '@/components/Button'
export default {
  components: {
    btn
  },
  data() {
    return {
      alertOpen: true,
      navBarSelection: null
    }
  },
  methods: {
    isNavButtonSelected(name) {
      if (name === this.navBarSelection) {
        return true
      }
    },
    navBarSelect(name) {
      if (this.navBarSelection === name) {
        this.navBarSelection = null
      } else {
        this.navBarSelection = name
      }
    }
  },
  computed: {
    getAlertText() {
      return 'FREE SHIPPING ON YOUR FIRST ORDER AND ANY ORDER OVER $89'
    },
    getAlertButtonText() {
      return 'CLICK TO SEE DETAILS'
    },
    menuOpen() {
      if (this.navBarSelection !== null) {
        return true
      } else {
        return false
      }
    }
  }
}
</script>

<style scoped>
.footer__column {
  width: 180px;
}
.footer__column h5 {
  margin-top: 0;
  font-weight: bold;
  font-size: 1.0em;
}
.footer-button {
  margin: 5px 0;
  cursor: pointer;
  font-size: 0.9em;
  background-color: transparent;
  color: #333;
  border: none;
  height: 25px;
  padding: 0;
  text-align: left;
}
.footer-button:hover {
  color: #F15B4B;
}
.footer-button--selected {
  color: #F15B4B;
}
.footer {
  border-top: 1px solid #E1E1E1;
  padding: 60px;
  display: flex;
  justify-content: center;
}
.footer__bottom {
  border-top: 1px solid #E1E1E1;
  padding: 20px;
  font-size: 0.9em;
  color: #AAA;
  background-color: #EEE;
  display: flex;
  justify-content: space-between;
}
.footer__bottom__button-container {
  display: flex;
  width: 250px;
  justify-content: space-between;
  cursor: pointer;
}
.footer__email-input {
  margin-right: 150px;
}
.footer__email-input h3 {
  margin-top: 0;
}
.footer__email-input__field-and-button-container input {
  box-sizing: border-box;
  height: 40px;
  padding: 0 5px;
  margin: 0 10px 0 0;
  outline: none;
  border: 1px solid #CCC;
}
.footer__email-input__field-and-button-container input::placeholder {
  color: #AAA;
}
.header {
  z-index: 300;
  position: relative;
  width: 100%;
}
.nav-bar__image {
  padding: 0;
  margin: 0; 
}
.nav-bar__menu {
  position: absolute;
  z-index: 200;
  display: flex;
  justify-content: space-between;
  width: 100%;
  background-color: white;
}
.nav-bar__menu__column {
  display: flex;
  flex-direction: column;
  margin-top: 15px;
}
.nav-bar__menu__column:first-child {
  margin-left: 12%;
}

.nav-bar__menu__column h1 {
  margin: 5px 0;
  font-size: 0.9em;
  font-weight: 500;
  height: 25px;
}
.nav-bar__menu__button {
  margin: 5px 0;
  cursor: pointer;
  font-size: 0.8em;
  background-color: transparent;
  color: #333;
  border: none;
  height: 25px;
  padding: 0;
  text-align: left;
}
.nav-bar__menu__button:hover {
  color: #F15B4B;
}
.nav-bar__logo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 350px;
}
.nav-bar__cart {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav-bar__cart__amount {
  font-size: 0.8em;
  color: #F15B4B;
}
.nav-bar__title {
  color: #222;
  font-weight: bold;
  font-size: 1.8em;
  line-height: 1.0em;
  letter-spacing: 1px;
}
.nav-bar__subtitle {
  color: #222;
  font-size: 1.2em;
  line-height: 1.0em;
  letter-spacing: 3px;
}
.vertical-divider {
  height: 40px;
  width: 1px;
  background-color: #CCC;
}
.nav-bar {
  z-index: 300;
  padding: 0 25px;
  height: 70px;
  background-color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #E1E1E1;
}
.nav-bar__button {
  cursor: pointer;
  font-size: 0.8em;
  background-color: transparent;
  color: #333;
  border: none;
  margin: 0 5px;
  height: 35px;
}
.nav-bar__button:hover {
  color: #F15B4B;
}
.nav-bar__button--selected {
  color: #F15B4B;
}
.nav-bar__button--small {
  cursor: pointer;
  font-size: 0.8em;
  font-weight: 300;
  margin: 0;
}
.alert-bar {
  font-family: 'Oxygen', sans-serif;
  font-weight: 300;
  background-color: #231F1F;
  font-size: 0.8em;
  color: #DDD;
  height: 40px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 1s;
  overflow: hidden;
}
.alert-bar__cta-button {
  color: white;
  font-weight: bold;
  text-decoration: underline;
  cursor: pointer;
}
.alert-bar__close-button__container {
  position: absolute;
  right: 0;
}
.alert-bar__close-button {
  background-color: transparent;
  border: none;
  margin: 5px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
.slide-up-enter-active, .slide-up-leave-active {
  transition: all 1s;
}
.slide-up-enter /* .list-leave-active below version 2.1.8 */ {
  transform: translateY(20px);
  height: 40px;
}
.slide-up-leave-to {
  transform: translateY(-20px);
  height: 0px;
}

.menu-slide-enter-active, .menu-slide-leave-active {
  transition: all 0.5s;
}
.menu-slide-enter /* .list-leave-active below version 2.1.8 */ {
  transform: translateY(-100%);
}
.menu-slide-leave-to {
  transform: translateY(-100%);
}
</style>
