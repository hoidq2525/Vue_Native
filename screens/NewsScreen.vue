<template>
  <view class="container">
    <FlatList/>
    <button title="Go to home screen" @press="goToHomeScreen"></button>
  </view>
</template>

<script>
import FlatList from './../component/FlatList'
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
      FlatList,
  },
}
</script>

<style>
.container {
  flex: 1;
}
</style>