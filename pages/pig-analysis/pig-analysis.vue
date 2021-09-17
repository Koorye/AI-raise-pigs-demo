<template>
  <view class="container">
    <view style="color: red;text-align: center; font-weight: bold; margin-top: 25rpx;">如果图表未显示，请重新进入</view>
    <view class="chart-box">
      <view class="chart">
        <view>健康比例：<text style="color: #4CD964;">80%</text></view>
        <qiun-data-charts type="pie" :chartData="chartData" />
      </view>
      <view class="line"></view>
      <view class="chart">
        <view>年龄结构：<text style="color: #4CD964;">增长型</text></view>
        <qiun-data-charts type="pie" :chartData="chartData2" />
      </view>
      <view style="text-align: center;">更多图表开发中...</view>
    </view>
    <view style="font-size: 10rpx; text-align: center;">Copyright © 2021 Koorye. All rights reserved.</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        chartData: {
          "series": [{
            "data": [{
              'name': '健康',
              'value': 80,
            }, {
              'name': '生病',
              'value': 20,
            }]
          }]
        },
        chartData2: {
          "series": [{
            "data": [{
              'name': '0~3个月',
              'value': 50,
            }, {
              'name': '3~6个月',
              'value': 30,
            }, {
              'name': '6~9个月',
              'value': 20,
            }, {
              'name': '9~12个月',
              'value': 30,
            }, {
              'name': '1岁以上',
              'value': 10,
            }]
          }]
        }
      }
    },
    methods: {

    }
  }
</script>

<style>
  .chart-box {
    margin: 100rpx 5%;
  }

  .chart {
    margin: 5% 0;
  }
  
  .line {
    width: 100%;
    height: 1rpx;
    /* margin: 0 5%; */
    background-color: #808080;
  }
</style>
