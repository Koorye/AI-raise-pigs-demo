<template>
  <view>
    <view class="user-box">
      <view>
        <image class="avatar" src="../../static/avatar/1.jpeg"></image>
      </view>
      <view>社会你猪哥</view>
      <view class="edit">编辑 ></view>
    </view>

    <view class="tool-list">
      <view style="color: red; font-weight: bold; text-align: center;">本页仅作展示，所有按钮均无实际作用(除退出按钮外)</view>
      <view class="tool-line">
        <view>
          <image src="../../static/index.png"></image>
        </view>
        <view>个人中心</view>
        <view></view>
        <view></view>
        <view></view>
        <view class="edit"> > </view>
      </view>
      <view class="line"></view>
      <view class="tool-line">
        <view>
          <image src="../../static/message.png"></image>
        </view>
        <view>我的消息</view>
        <view></view>
        <view></view>
        <view></view>
        <view class="edit"> > </view>
      </view>
      <view class="line"></view>
      <view class="tool-line">
        <view>
          <image src="../../static/bill.png"></image>
        </view>
        <view>我的账单</view>
        <view></view>
        <view></view>
        <view></view>
        <view class="edit"> > </view>
      </view>
      <view class="line"></view>
      <view class="tool-line">
        <view>
          <image src="../../static/star.png"></image>
        </view>
        <view>我的收藏</view>
        <view></view>
        <view></view>
        <view></view>
        <view class="edit"> > </view>
      </view>
      <view class="line"></view>
      <view class="tool-line">
        <view>
          <image src="../../static/feedback.png"></image>
        </view>
        <view>意见反馈</view>
        <view></view>
        <view></view>
        <view></view>
        <view class="edit"> > </view>
      </view>
      <view class="line"></view>
      <view class="tool-line" @tap="logout">
        <view>
          <image src="../../static/sign-out.png"></image>
        </view>
        <view>退出登录</view>
        <view></view>
        <view></view>
        <view></view>
        <view class="edit"> > </view>
      </view>
    </view>
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
      logout() {
        uni.showToast({
          title: "正在退出",
          icon: "loading"
        })
        setTimeout(() => {
          uni.showToast({
            title: "退出成功",
            icon: "success"
          })
        }, 2000)
        setTimeout(() => {
          uni.redirectTo({
            url: '../login/login'
          })
        }, 3000)
      }
    }
  }
</script>

<style>
  image {
    width: 50rpx;
    height: 50rpx;
  }

  .user-box {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 75rpx 5%;
    background-color: coral;
    color: white;
    font-size: 30rpx;
    font-weight: bold;
  }

  .avatar {
    width: 200rpx;
    height: 200rpx;
    border-radius: 50%;
  }

  .edit {
    text-align: right;
  }

  .tool-list {
    margin: 10% 5%;
    font-size: 30rpx;
  }

  .tool-line {
    margin: 5% 0;
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .line {
    width: 100%;
    height: 1rpx;
    background-color: #808080;
  }
</style>
