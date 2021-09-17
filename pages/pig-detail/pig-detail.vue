<template>
  <view>
    <view style="color: red;text-align: center; font-weight: bold; margin-top: 25rpx;">当前页面仅为展示，所有小猪都展示此页面</view>
    <view style="color: red;text-align: center; font-weight: bold; margin-top: 25rpx;">如果图表未显示，请重新进入</view>
    <view class="top-box">
      <image src="../../static/avatar/1.jpeg" mode="aspectFill"></image>
      <view>狗蛋</view>
      <view></view>
      <view></view>
      <view></view>
      <view style="height: 100rpx; width: 1rpx; background-color: #808080;"></view>
      <view class="info-tag-box">
        <view>性别: </view>
        <view>猪龄: </view>
        <view>身体状况: </view>
      </view>
      <view class="info-box">
        <view>母猪</view>
        <view>8个月</view>
        <view><text style="color: #4CD964; font-weight: bold;">健康</text></view>
      </view>
    </view>
    <view class="line"></view>
    <view class="chart-box">
      <view class="chart">
        <view>体重变化：<text style="color: #4CD964;">符合标准</text></view>
        <qiun-data-charts type="line" :chartData="chartData" />
      </view>
      <view class="line"></view>
      <view class="chart">
        <view>每日进食： <text style="color: #4CD964;">符合标准</text></view>
        <qiun-data-charts type="line" :chartData="chartData2" />
      </view>
      <view class="line"></view>
      <view class="chart">
        <view>每日饮水： <text style="color: #4CD964;">符合标准</text></view>
        <qiun-data-charts type="line" :chartData="chartData3" />
      </view>
    </view>
    <view style="font-size: 10rpx; text-align: center;">Copyright © 2021 Koorye. All rights reserved.</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        chartData: {
          categories: ["9-12", "9-13", "9-14", "9-15", "昨天", "今天"],
          series: [{
            name: "实际体重(Kg)",
            data: [85.5, 85.8, 86.1, 86.2, 86.4, 86.7]
          }, {
            name: "标准体重(Kg)",
            data: [85, 85.5, 85.9, 86.2, 86.5, 86.7, 86.9]
          }]
        },
        chartData2: {
          categories: ["9-12", "9-13", "9-14", "9-15", "昨天", "今天"],
          series: [{
            name: "实际进食(Kg)",
            data: [8.9, 8.7, 9.2, 9.3, 9.5, 9.4]
          }, {
            name: "标准进食(Kg)",
            data: [8.9, 9, 9.1, 9.2, 9.2, 9.3]
          }]
        },
        chartData3: {
          categories: ["9-12", "9-13", "9-14", "9-15", "昨天", "今天"],
          series: [{
            name: "实际饮水(L)",
            data: [3.5, 3.8, 3.4, 3.6, 3.5, 3.7]
          }, {
            name: "标准饮水(L)",
            data: [3.2, 3.3, 3.4, 3.5, 3.5, 3.6]
          }]
        }
      }
    },
    methods: {

    }
  }
</script>

<style>
  image {
    width: 150rpx;
    height: 150rpx;
    margin: 25rpx;
    border-radius: 50%;
  }

  .top-box {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-weight: bold;
    margin: 0 5%;
  }

  .info-tag-box {
    text-align: left;
    font-size: 20rpx;
  }

  .info-box {
    text-align: right;
    font-size: 20rpx;
    font-weight: 400;
  }

  .chart-box {
    margin: 5% 5%;
    font-weight: bold;
    text-align: center;
  }

  .chart {
    margin: 5% 0;
  }

  .line {
    width: 90%;
    height: 1rpx;
    margin: 0 5%;
    background-color: #808080;
  }
</style>
