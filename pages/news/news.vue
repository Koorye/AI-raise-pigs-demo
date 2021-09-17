<template>
  <view>
    <uni-list>
      <uni-list-item direction="row" v-for="item,id in info" :key="id" :title="item.title"
        :note="item.user_name + ' '+item.last_modify_date">
        <!-- 通过v-slot:header插槽定义列表左侧的图片显示，其他内容通过List组件内置属性实现-->
        <template v-slot:header>
          <!-- 当前判断长度只为简单判断类型，实际业务中，根据逻辑直接渲染即可 -->
          <image class="image-1" :src="item.avatar" mode="aspectFill"></image>
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
        info: [{
            "user_name": "未来汽车日报",
            "title": "为什么自动驾驶诉讼不断？",
            "avatar": "../../static/swiper/1.jpeg",
            "last_modify_date": "2020-04-11 17:11:09",
          },
          {
            "user_name": "36氪深度服务",
            "title": "2020数字中国创新大赛-数字政府赛道21强出炉，四大赛题紧贴政府数字化发展需求",
            "avatar": "../../static/swiper/2.jpeg",
            "last_modify_date": "2020-04-11 17:03:18",
          }, {
            "user_name": "未来汽车日报",
            "title": "地方政府救市哪家强？广州补贴上万元，广深杭新增指标超5万",
            "avatar": "../../static/swiper/3.jpeg",
            "last_modify_date": "2020-04-11 16:11:11",
          },{
            "user_name": "未来汽车日报",
            "title": "为什么自动驾驶诉讼不断？",
            "avatar": "../../static/swiper/1.jpeg",
            "last_modify_date": "2020-04-11 17:11:09",
          },
          {
            "user_name": "36氪深度服务",
            "title": "2020数字中国创新大赛-数字政府赛道21强出炉，四大赛题紧贴政府数字化发展需求",
            "avatar": "../../static/swiper/2.jpeg",
            "last_modify_date": "2020-04-11 17:03:18",
          }, {
            "user_name": "未来汽车日报",
            "title": "地方政府救市哪家强？广州补贴上万元，广深杭新增指标超5万",
            "avatar": "../../static/swiper/3.jpeg",
            "last_modify_date": "2020-04-11 16:11:11",
          },{
            "user_name": "未来汽车日报",
            "title": "为什么自动驾驶诉讼不断？",
            "avatar": "../../static/swiper/1.jpeg",
            "last_modify_date": "2020-04-11 17:11:09",
          },
          {
            "user_name": "36氪深度服务",
            "title": "2020数字中国创新大赛-数字政府赛道21强出炉，四大赛题紧贴政府数字化发展需求",
            "avatar": "../../static/swiper/2.jpeg",
            "last_modify_date": "2020-04-11 17:03:18",
          }, {
            "user_name": "未来汽车日报",
            "title": "地方政府救市哪家强？广州补贴上万元，广深杭新增指标超5万",
            "avatar": "../../static/swiper/3.jpeg",
            "last_modify_date": "2020-04-11 16:11:11",
          }]
      }
    },
    methods: {

    }
  }
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.image-1 {
		flex-shrink: 0;
		margin-right: 10px;
		width: 125px;
		height: 75px;
		border-radius: 6px;
		overflow: hidden;
		border: 1px #f5f5f5 solid;
	}
</style>
