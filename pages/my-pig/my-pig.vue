<template>
  <view class="container">
    <uni-search-bar placeholder="搜索要找的小猪(不可用,仅作展示)"></uni-search-bar>
    <uni-list>
      <uni-list-item title="狗蛋" note="性别: 公猪; 猪龄: 3个月; 身体状况: 健康" @tap="toPigDetail" link>
        <template v-slot:header>
          <image src="../../static/avatar/1.jpeg" mode="aspectFill"></image>
        </template>
      </uni-list-item>
      <uni-list-item title="猫蛋" note="性别: 母猪; 猪龄: 6个月; 身体状况: 健康" @tap="toPigDetail" link>
        <template v-slot:header>
          <image src="../../static/avatar/2.jpeg" mode="aspectFill"></image>
        </template>
      </uni-list-item>
      <uni-list-item title="鸡蛋" note="性别: 公猪; 猪龄: 2个月; 身体状况: 健康" @tap="toPigDetail" link>
        <template v-slot:header>
          <image src="../../static/avatar/3.jpeg" mode="aspectFill"></image>
        </template>
      </uni-list-item>
      <uni-list-item title="鸭蛋" note="性别: 母猪; 猪龄: 8个月; 身体状况: 健康" @tap="toPigDetail" link>
        <template v-slot:header>
          <image src="../../static/avatar/4.jpeg" mode="aspectFill"></image>
        </template>
      </uni-list-item>
    </uni-list>
    <view style="font-size: 10rpx; text-align: center;">Copyright © 2021 Koorye. All rights reserved.</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {

      }
    },
    methods: {
      toPigDetail() {
        uni.navigateTo({
          url: '../pig-detail/pig-detail'
        })
      }
    }
  }
</script>

<style>
  image {
    width: 150rpx;
    height: 150rpx;
    margin: 0 25rpx;
    margin-left: 0;
    border-radius: 50%;
  }

  .container {
    margin: 0 5%;
  }
</style>
