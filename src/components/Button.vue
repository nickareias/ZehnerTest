<template>
  <button :class="{'small-button': small}" @click="click()">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    small: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    click() {
      this.$emit('click')
    }
  }
}
</script>

<style scoped>
.small-button {
  padding: 0 20px;
  height: 40px;
  font-size: 0.9em;
  min-width: 100px;
}
button {
  border: 1px solid #F15B4B;
  color: #F15B4B;
  font-weight: bold;
  cursor: pointer;
  outline: none;
  background-color: transparent;
  padding: 15px 30px;
  min-width: 150px;
}
button:hover {
  background-color: #F15B4B;
  color: white;
}
button:active {
  background-color: #F15B4B;
  color: white;
}
</style>
