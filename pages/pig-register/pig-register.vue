<template>
  <view>
    <view class="photo-list">
      <view class="photo-line">
        <view>
          <image class="photo" :src="photo1"></image>
        </view>
        <view>为小猪拍摄正面照</view>
        <view @tap="takePhoto1">
          <image class="camera" src="../../static/camera.png"></image>
        </view>
      </view>
      <view class="line"></view>
      <view class="photo-line">
        <view>
          <image class="photo" :src="photo2"></image>
        </view>
        <view>为小猪拍摄侧面照</view>
        <view @tap="takePhoto2">
          <image class="camera" src="../../static/camera.png"></image>
        </view>
      </view>
      <uni-easyinput placeholder="为小猪取个名字吧"></uni-easyinput>
      <view style="height: 25rpx"></view>
      <uni-datetime-picker placeholder="为小猪设置生日吧"></uni-datetime-picker>
    </view>
    <view class="upload" @tap="upload">
      <image src="../../static/upload.png"></image>
      <view>上传信息</view>
    </view>
    <view style="font-size: 10rpx; text-align: center;">Copyright © 2021 Koorye. All rights reserved.</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        photo1: '../../static/photo.png',
        photo2: '../../static/photo.png'
      }
    },
    methods: {
      takePhoto1() {
        uni.chooseImage({
          count: 1,
          sizeType: ['original', 'compressed'],
          sourceType: ['camera', 'album'], //这要注意，camera掉拍照，album是打开手机相册
          success: (res) => {
            this.photo1 = res.tempFilePaths[0];
          }
        });
      },
      takePhoto2() {
        uni.chooseImage({
          count: 1,
          sizeType: ['original', 'compressed'],
          sourceType: ['camera', 'album'], //这要注意，camera掉拍照，album是打开手机相册
          success: (res) => {
            this.photo2 = res.tempFilePaths[0];
          }
        });
      },
      upload() {
        uni.showToast({
          title: "正在上传",
          icon: "loading"
        })
        setTimeout(()=> {
          uni.showToast({
            title: "上传成功",
            icon: "success"
          })
        }, 2000)
        setTimeout(()=> {
          uni.navigateBack({
            animationType: "pop-out",
            animationDuration: 500
          })
        },2500)
      }
    }
  }
</script>

<style>
  image {
    width: 100rpx;
    height: 100rpx;
  }

  .photo {
    width: 200rpx;
    height: 200rpx;
    padding: 5%;
    border: 3px dashed;
  }

  .camera {
    width: 100rpx;
    height: 100rpx;
  }

  .photo-list {
    margin: 5%;
  }

  .photo-line {
    margin: 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 25rpx;
    font-weight: bold;
  }

  .upload {
    margin: 25rpx 40%;
    font-size: 25rpx;
    font-weight: bold;
    text-align: center;
  }

  .line {
    height: 1rpx;
    background-color: #808080;
  }
</style>
