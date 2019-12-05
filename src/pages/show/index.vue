<template>
  <div>
  
<i-card title="哈哈" extra="..." thumb="/static/images/001.png">
    <view slot="content"><image src="/static/images/20.jpg"></image></view>
   <view slot="footer">
   123
   </view>
  
</i-card>
<i-card title="哈皮" extra="..." thumb="/static/images/002.jpg">
    <view slot="content"><image src="/static/images/20.jpg"></image></view>
    <view slot="footer">不错哦 点赞</view>
</i-card>
<i-card title="11" extra="..." thumb="/static/images/003.png">
    <view slot="content">   
       <swiper autoplay circle indicator-dots>
 
      <swiper-item>
        <image src="/static/images/20.jpg" ></image>
      </swiper-item>
  

      <swiper-item>
        <image src="/static/images/21.jpg" ></image>
      </swiper-item>
   
      </swiper>
       
    <view slot="footer">喜欢 点赞</view>
</i-card>
<i-card title="23" extra="..." thumb="/static/images/004.png">
    <view slot="content"><image src="/static/images/20.jpg"></image></view>
    <view slot="footer">爱了爱了</view>
</i-card>

<i-panel title="基础用法">
    <i-input value="{{ value1 }}" title="收货人" autofocus placeholder="名字" />
    <i-input value="{{ value2 }}" type="number" title="联系电话" placeholder="请输入手机号" />
    <i-input value="{{ value3 }}" type="textarea" title="详细地址" placeholder="请输入详细地址(最多50字)" maxlength="50" />
    <i-input value="{{ value4 }}" title="用户信息" disabled />
</i-panel>

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
