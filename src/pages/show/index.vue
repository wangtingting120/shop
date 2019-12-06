<template>
  <div>
  
<i-card title="哈哈" extra="..." thumb="/static/images/001.png">
    <view slot="content">
      <swiper autoplay circular indicator-dots>
      <swiper-item>
      <image src="/static/images/24.jpg" mode="widthFix" ></image>
      </swiper-item>
       <swiper-item>
      <image src="/static/images/25.jpg" mode="widthFix" ></image>
      </swiper-item>
      </swiper>
      </view>
    <view slot="footer">不错哦 点赞</view>
</i-card>
<i-card title="哈皮" extra="..." thumb="/static/images/002.jpg">
    <view slot="content">
      <swiper autoplay circular indicator-dots>
      <swiper-item>
      <image src="/static/images/21.jpg" mode="widthFix"></image>
      </swiper-item>
       <swiper-item>
      <image src="/static/images/20.jpg" mode="widthFix"  style="width:100%"></image>
      </swiper-item>
      </swiper>
      </view>
    <view slot="footer">不错哦 点赞</view>
</i-card>
<i-card title="哈皮" extra="..." thumb="/static/images/003.png">
    <view slot="content"><image src="/static/images/22.jpg" mode="widthFix"></image></view>
    <view slot="footer">不错哦 点赞</view>
</i-card>
<i-card title="23" extra="..." thumb="/static/images/004.png">
    <view slot="content"><image src="/static/images/23.jpg" mode="widthFix"></image></view>
    <view slot="footer">爱了爱了</view>
</i-card>



</div>
 
</template>

<script>


export default {
  data () {
    return {
     
     
      
      }
   
  },

  methods: {


    
   
    },

  created () {
 
  }
}
</script>

<style scoped>

swiper swiper-item{
  width:100%;
}
image{
  width:100%;
}
</style>
