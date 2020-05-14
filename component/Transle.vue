<template>
  <view class="container">
    <StatusBar hidden/>
    <view class="input1">
      <text class="textbox">Nhập chữ China:</text>
      <text-input multiline class="input-text" v-model="text" />
    </view>
    <view class="input3">
      <view class="button-type">
        <button
          :on-press="onPressPhare"
          title="Dịch Phare"
          color="#841584"
          accessibility-label="Learn more about this purple button"
        />
      </view>
      <view class="button-type">
        <button
          :on-press="onPressHanViet"
          title="Dịch Hán Việt"
          accessibility-label="Learn more about this purple button"
        />
      </view>
    </view>

    <view class="input2">
      <text class="textbox">Kết quả:</text>
      <TextInput  class="input-text" v-model="text2" multiline />
     
    </view>
  </view>
</template>

<script>
import axios from "axios";
import { TextInput,StatusBar } from 'react-native';
export default {
  data: function() {
    return {
      text:
        " 先秦兩漢 先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢 先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢先秦兩漢",
      text2: ""
    };
  },
  methods: {
    onPressPhare() {
      let url = "http://www.vietphrase.info/Vietphrase/TranslateVietPhraseS";
      this.CallAPi(url);
    },
    onPressHanViet() {
      let url = "http://www.vietphrase.info/Vietphrase/TranslateHanViet";
      this.CallAPi(url);
    },
    CallAPi(url, types) {
      axios
        .post(url, {
          chineseContent: this.text
        })
        .then(response => {
          this.text2 = response.data;
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>

<style>
.container {
  background-color: rgb(131, 118, 118);
  align-items: center;
  justify-content: center;
  flex: 1;
}
.input1 {
  margin-top: 30px;
  background-color: rgb(248, 245, 245);
  width: 98%;
  flex: 1;
}

.input2 {
  margin-top: 5px;
  background-color: rgb(248, 245, 245);
  width: 98%;
  flex: 2;
}
.input3 {
  background-color: forestgreen;
  flex: 0;
  flex-direction: row;
}
.textbox {
  text-align: center;
  color: rgb(12, 10, 134);
}
.input-text {
  background-color:antiquewhite ;
  padding: 10px;
  color: rgb(8, 8, 8);
  text-transform: capitalize;
  border-radius: 25px;
  height: 90%;
  border-color:grey;
  border-width: 1;
}
.button-type {
  flex: 1;
}
</style>