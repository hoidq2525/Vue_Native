<template>
  <view class="container">
    <scroll-view :content-container-style="{contentContainer: {
        paddingVertical: 20
    }}">
      <view class="content" v-for="da in mang" :key="da.object_id">
        <Text class="title">{{da.title}}</Text>
        <image class="img" :source="{uri: da.thumb_link}" />
        <Text class="des">{{da.description}}</Text>
      </view>
      <activity-indicator v-if="showload" size="large" color="#0000ff" />
      <button title="Loadmore demo" @press="Loadmore"></button>
    </scroll-view>
  </view>
</template>

<script>
import React, { Component } from "react";
import { View, Text, Image } from "react-native";
import axios from "axios";
export default {
  data: function() {
    return {
      mang: [],
      num: 1,
      showload: false
    };
  },
  created() {
    this.CallAPi(1);
  },
  methods: {
    Loadmore() {
      let vm = this;
      vm.showload = true;
      let page = vm.num++;
      setTimeout(() => {
        vm.CallAPi(page, true);
        vm.showload = false;
      },1000);
    },
    async CallAPi(page, loadmore = false) {
      await axios
        .get(
          `https://api.tuoitre.vn/mobileapp/catpage?token=da039e81&limit=5&page=${page}&prior=1&cid=7`
        )
        .then(response => {
          if (loadmore) {
            this.mang = this.mang.concat(response.data);
          } else {
            this.mang = response.data;
          }
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
  flex: 1;
  justify-content: center;
  align-items: center;
}
.flast {
  padding-top: 30px;
  flex: 1;
}
.content {
  padding-bottom: 10px;
  border-color: rgb(142, 146, 144);
  border-width: 0.5px;
  padding-left: 10px;
}
.img {
  height: 50px;
  width: 50px;
  top: 10px;
}
.title {
  color: red;
  font-size: 18px;
}
.des {
  position: relative;
  margin: 5px;
  padding-left: 60px;
  top: -50px;
}
</style>
