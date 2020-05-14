<template>
  <View class="container">
    <View class="dong">
      <View class="cot">
        <Text class="number">1</Text>
      </View>
      <View class="cot">
        <Text class="number">2</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">3</Text>
        <Text class="string">ABC</Text>
      </View>
    </View>

    <View class="dong">
      <View class="cot">
        <Text class="number">4</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">5</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">6</Text>
        <Text class="string">ABC</Text>
      </View>
    </View>

    <View class="dong">
      <View class="cot">
        <Text class="number">7</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">8</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">9</Text>
        <Text class="string">ABC</Text>
      </View>
    </View>

    <View class="dong">
      <View class="cot">
        <Text class="number">0</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">#</Text>
        <Text class="string">ABC</Text>
      </View>
      <View class="cot">
        <Text class="number">2</Text>
        <Text class="string">ABC</Text>
      </View>
    </View>
  </View>
</template>
<script>
export default {};
</script>
<style>
.container {
  flex: 1;
}
.dong {
  flex: 1;
  border-bottom-color: gray;
  border-bottom-width: 1;
  flex-direction: row;
}
.cot {
  flex: 1;
  border-right-width: 1;
  border-color: black;
  justify-content: center;
  align-items: center;
}
.number {
  font-size: 60px;
}
.string {
  font-size: 30px;
}
</style>