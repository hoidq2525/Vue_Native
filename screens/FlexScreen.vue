<template>
  <view class="container">
    <Flex />
    <button title="Go to home screen" @press="goToHomeScreen"></button>
  </view>
</template>

<script>
import Flex from "./../component/Flex";
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
    Flex
  }
};
</script>

<style>
.container {
  flex: 1;
}
</style>