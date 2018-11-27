<template>
  <div id="app">
    <component :is="getLayout">
      <router-view></router-view>
    </component>
  </div>
</template>

<script>
import HomeLayout from '@/layouts/HomeLayout'
export default {
  computed: {
    getLayout() {
      return HomeLayout
    }
  }
}
</script>


<style>
body {
  padding: 0;
  margin: 0;
  overflow-x: hidden;
}
#app {
  color: #2A2A2A;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  font-family: 'Noto Sans SC', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.horizontal-divider {
  width: 40px;
  height: 1px;
  background-color: #F15B4B;
  margin: 25px 0;
}
</style>
