<template>
  <view>
    <view class="msgBanner">
      <view>
        <image class="bannerImg" src="/static/voice.png"></image>
      </view>
      <view>{{ bannerMsg }}</view>
    </view>
    <view class="swiper-box">
      <swiper indicator-dots circular autoplay interval=3000>
        <swiper-item v-for="(item,index) in swipers" :key="index">
          <image class="top-image" :src="item"></image>
        </swiper-item>
      </swiper>
    </view>
    <view class="button-line">
      <view class="image-box" @tap="toPigRegister">
        <image src="../../static/register.png"></image>
        <view>新猪入栏</view>
      </view>
      <view class="image-box" @tap="toMyPig">
        <image src="../../static/list.png"></image>
        <view>我的小猪</view>
      </view>
      <view class="image-box" @tap="toPigAnalysis">
        <image src="../../static/analysis.png"></image>
        <view>猪栏分析</view>
      </view>
    </view>
    <view class="line"></view>
    <!-- <view style="color: red;text-align: center; font-weight: bold; margin-top: 25rpx;">(上述三个按钮可用)下列按钮仅作展示，不可用</view> -->
    <view class="button-line">
      <view class="image-box" @tap="todo">
        <image src="../../static/market.png"></image>
        <view>市场分析</view>
      </view>
      <view class="image-box" @tap="todo">
        <image src="../../static/education.png"></image>
        <view>养猪教程</view>
      </view>
      <view class="image-box" @tap="todo">
        <image src="../../static/question.png"></image>
        <view>问题咨询</view>
      </view>
    </view>
    <view style="font-size: 10rpx; text-align: center;">Copyright © 2021 Koorye. All rights reserved.</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Hello',
        bannerMsg: '',
        swipers: [
          '../../static/swiper/1.jpeg',
          '../../static/swiper/2.jpeg',
          '../../static/swiper/3.jpeg'
        ]
      }
    },
    onLoad() {
      
    },
    created() {
      let msg = '疫情期间，请做好防控工作：1.做好消毒工作，2.保持合理的饲养密度，3.提高物资储备，防止霉变中毒，4.寻求畜牧主管机构援助。';
      let msg2 = msg + '  ' + msg
      let that = this;
      let startPos = 0;
      setInterval(function() {
        that.bannerMsg = msg2.substr(startPos, 29);
        ++startPos;
        if (startPos == msg.length) startPos = 0;
      }, 250);
    },
    methods: {
      toPigRegister() {
        uni.navigateTo({
          url: '../pig-register/pig-register'
        })
      },
      toMyPig() {
        uni.navigateTo({
          url: '../my-pig/my-pig'
        })
      },
      toPigAnalysis() {
        uni.navigateTo({
          url: '../pig-analysis/pig-analysis'
        })
      },
      todo() {
        uni.showToast({
          title: '功能开发中',
          icon: 'error'
        })
      }
    }
  }
</script>

<style>
  image {
    width: 100rpx;
    height: 100rpx;
  }
  
  .msgBanner {
    /* z-index: 999; */
    display: flex;
    align-items: center;
    width: 100%;
    height: 60rpx;
    color: #fffdef;
    font-size: 24rpx;
    font-weight: bold;
    background-color: rgba(0, 0, 0, 0.5);
    /* position: fixed; */
  }
  
  .bannerImg {
    width: 40rpx;
    height: 40rpx;
    margin-right: 20rpx;
  }

  .swiper-box {
  }

  .top-image {
    margin: 5%;
    width: 90%;
    height: 300rpx;
    border-radius: 30rpx;
  }

  .button-line {
    display: flex;
    justify-content: space-around;
    text-align: center;
    width: 90%;
    margin: 10% 5%;
    font-size: 30rpx;
    font-weight: bold;
  }

  .line {
    width: 90%;
    height: 1rpx;
    margin: 0 5%;
    background-color: #808080;
  }
</style>
