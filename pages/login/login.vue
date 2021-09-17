<template>
  <view class="container">
    <view style="height: 150rpx;"></view>
    <!-- Logo -->
    <view class="logo-box">
      <view>
        <image class="logo" src="../../static/icon.png"></image>
      </view>
      <view>AI智能养猪平台</view>
      <view>登录</view>
    </view>

    <view class="login-box">
      <view style="font-size: 20rpx; text-align: center; color: red; font-weight: bold;">预览版本无需输入用户名密码，直接登录即可</view>
      <uni-easyinput placeholder="请输入用户名"></uni-easyinput>
      <view style="height: 25rpx;"></view>
      <uni-easyinput placeholder="请输入密码"></uni-easyinput>
      <view style="height: 25rpx;"></view>
      <navigator class="forget-password" @tap="todo">忘记密码?</navigator>
      <view style="height: 25rpx;"></view>
      <view class="button-box">
        <button @tap="login" :loading="loading">登录</button>
        <button @tap="todo">注册</button>
      </view>
    </view>
    <view class="version-box">Version: {{ version }}</view>
    <view style="font-size: 10rpx; text-align: center;">Copyright © 2021 Koorye. All rights reserved.</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        username: '',
        password: '',
        version: 'V0.0.1-SNAPSHOT',
        loading: false
      }
    },
    methods: {
      login() {
        this.loading = true;
        uni.showToast({
          icon: 'loading',
          title: '正在登录'
        })
        setTimeout(() => {
          uni.switchTab({
            url: '../index/index'
          })
          uni.showToast({
            icon: 'success',
            title: '登录成功'
          })
        }, 1500)
      },
      todo() {
        uni.showToast({
          icon: 'error',
          title: '功能正在开发中'
        })
      }
    }
  }
</script>

<style>
  image {
    width: 200rpx;
    height: 200rpx;
  }

  uni-easyinput {
    background-color: #F8F8F8;
  }

  button {
    background-color: coral;
    width: 40%;
    color: white;
  }

  .container {
    margin: 0 5%;
  }

  .logo-box {
    margin: 50rpx 0;
    text-align: center;
    color: coral;
    font-size: 40rpx;
    font-weight: bold;
  }

  .logo {
    border-radius: 50%;
    border: 5rpx solid coral;
    padding: 5%;
  }

  .login-box {
    padding: 5%;
    border-radius: 50rpx;
    border: 1rpx solid coral;
  }

  .button-box {
    display: flex;
    justify-content: space-between;
  }

  .forget-password {
    color: #007AFF;
    text-align: right;
    font-size: 20rpx;
  }

  .version-box {
    margin: 5%;
    font-weight: bold;
    font-size: 20rpx;
    text-align: center;
  }
</style>
