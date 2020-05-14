<template>
  <view class="container">
    <text>This is the Home screesn</text>
    <button title="1:Go to the Details screen" @press="changeRoute('Details')"></button>
    <button title="2:Dich" @press="changeRoute('Dich')"></button>
    <button title="3:News demo" @press="changeRoute('News')"></button>
    <button title="4:Flex demo" @press="changeRoute('Flex')"></button>
    <button title="5:Slot demo" @press="changeRoute('Slot')"></button>
    <button title="6:Loadmore demo" @press="changeRoute('Loadmore')"></button>
  </view>
</template>

<script>
export default {
  props: {
    navigation: { type: Object }
  },
  methods: {
    changeRoute(screen) {
      this.navigation.navigate(screen);
    }
  }
};
</script>

<style>
.container {
  align-items: center;
  justify-content: center;
  background-color: aquamarine;
  flex: 1;
}
</style>