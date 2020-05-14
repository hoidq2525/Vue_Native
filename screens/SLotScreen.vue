<template>
  <view class="container">
    <child>
      <text slot="top">Top text</text>
      <text slot="bottom">Bottom text</text>
      <text>Text with no name</text>
      <text slot="middle">Middle text</text>
    </child>
  </view>
</template>

<script>
import Child from "./../component/child";
export default {
  components: {
    Child
  },
  data: function() {
    return {};
  },
  mounted() {}
};
</script>

<style>
.container {
  background-color: white;

  align-items: center;

  justify-content: center;

  flex: 1;
}

.text-color-primary {
  color: blue;
}

.text-container {
  flex: 1;

  margin-bottom: 30;
}
</style>
