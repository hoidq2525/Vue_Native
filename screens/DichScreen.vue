<template>
  <view class="container">
    <Transle/>
    <button title="Go to home screen" @press="goToHomeScreen"></button>
  </view>
</template>

<script>
import Transle from './../component/Transle'
export default {
  props: {
    navigation: { type: Object }
  },
  methods: {
    goToHomeScreen() {
      this.navigation.navigate("Home");
    }
  },
  components: {
      Transle,
  },
}
</script>

<style>
.container {
  flex: 1;
}
</style>