<template>
  <button :style="getButtonStyle">
    <div class="filter">
      <p><slot></slot></p>
    </div>
  </button>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: ''
    },
    height: {
      type: String,
      default: 271
    },
    width: {
      type: String,
      default: 271
    }
  },
  computed: {
    getButtonStyle() {
      return {
        'background-image': 'url("' + this.image + '")',
        'height': this.height + 'px',
        'width': this.width + 'px'
      }
    }
  }
}
</script>

<style scoped>
.filter {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.filter:hover {
  background-color: rgba(255,255,255,0.75);
}
button {
  padding: 0;
  margin: 0;
  border: none;
  background-color: transparent;
  background-size: cover;
  background-position: center;
  color: transparent;
  font-weight: bold;
  cursor: pointer;
  box-sizing: border-box;
}
button:hover {
  color: #F15B4B;
  outline: 1px solid #F15B4B;
}
button:active {
  color: #F15B4B;
  outline: 1px solid #F15B4B;
}
button:focus {
  outline: 1px solid #F15B4B;
}
</style>
