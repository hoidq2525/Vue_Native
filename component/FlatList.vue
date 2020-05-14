<template>
  <view class="container">
    <!-- <scroll-view :content-container-style="{contentContainer: {
        paddingVertical: 20
    }}">
      <view class="content" v-for="da in mang" :key="da.object_id">
        <Text class="title">{{da.title}}</Text>
        <image class="img" :source="{uri: da.thumb_link}" />
        <Text class="des">{{da.description}}</Text>
      </view>
    </scroll-view> -->

    <!-- cach 1 render func  -->
    <!-- <flat-list
      :data="mang"
      :render-item="(item) => renderList(item)"
      :horizontal="ho"
      :numColumns="num"
    />-->
    <!-- cach 2 render truc tiep -->
    <flat-list :numColumns="1" class="flast" :data="mang">
      <View render-prop-fn="renderItem" v-bind:key="args.item.object_id">
        <Text :style="titleCss">{{args.item.title}}</Text>
        <image :style="imgCss" :source="{uri: args.item.thumb_link}" />
        <Text :style="desCss">{{args.item.description}}</Text>
      </View>
    </flat-list>
  </view>
</template>

<script>
import React, { Component } from "react";
import { View, Text, Image } from "react-native";
import axios from "axios";
export default {
  data: function() {
    return {
      ho: false,
      num: 3,
      mang: [],
      titleCss: {
        color: "red"
      },
      imgCss: {
        width: 100,
        height: 100
      },
      desCss: {
        color: "gray",
        marginLeft: 120,
        top: 150
      }
    };
  },
  created() {
    this.CallAPi(
      "https://api.tuoitre.vn/mobileapp/home?token=da039e81&type=20list"
    );
    // this.CallAPi('https://raw.githubusercontent.com/hoidq2525/Web_GM_Dj2/master/data/item_list.json')
  },
  methods: {
    // https://github.com/hoidq2525/Web_GM_Dj2/blob/master/data/item.json
    renderList: function(item) {
      return (
        <View>
          <Text>{item.item.key}</Text>
          <Image
            style={{
              width: 66,
              height: 58
            }}
            source={{
              uri: "https://reactnative.dev/img/tiny_logo.png"
            }}
          />
        </View>
      );
    },
    async CallAPi(url, types) {
      await axios
        .get(url)
        .then(response => {
          this.mang = response.data;
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
.content{
  padding-top:30px ;
  padding-bottom: 10px;
  border-color: rgb(142, 146, 144);
  border-width: 0.5px;
   padding-left: 10px;
}
.img{
  height: 50px;
  width: 50px;
  top:10px
}
.title{
  color: red;
  font-size:18px;
}
.des{
  position:relative;
  margin: 5px;
  padding-left: 60px;
  top:-50px
}
</style>
