<template>
  <div>
  
<i-card title="哈哈" extra="..." thumb="/static/images/001.png">
    <view slot="content"><image src="/static/images/20.jpg"></image></view>
    <view slot="footer">这件衣服很不错哦 点赞</view>
</i-card>
<i-card title="哈皮" extra="..." thumb="/static/images/002.jpg">
    <view slot="content"><image src="/static/images/20.jpg"></image></view>
    <view slot="footer">不错哦 点赞</view>
</i-card>
<i-card title="11" extra="..." thumb="/static/images/003.png">
    <view slot="content">   
       <swiper
    :indicator-dots="indicatorDots"
    :autoplay="autoplay"
    :interval="interval"
    :duration="duration"
    >
    <block>
      <swiper-item>
        <image src="/static/images/20.jpg"></image>
        <image src="/static/images/21.jpg"></image>
      </swiper-item>
      </block>
      </swiper></view>
    <view slot="footer">喜欢 点赞</view>
</i-card>
<i-card title="23" extra="..." thumb="/static/images/004.png">
    <view slot="content"><image src="/static/images/20.jpg"></image></view>
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

</style>
