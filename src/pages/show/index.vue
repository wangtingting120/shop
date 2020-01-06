<template>
  <div>

    <i-card>
    <view slot="content">
    <i-panel title="这是什么仙女穿搭，我要分享！">
      <i-input :value="name" @change="changeName($event)" title="穿搭风格" autofocus placeholder="请输入穿搭风格" maxlength="20" />
      <i-input :value="reason" @change="changeReason($event)" title="分享理由" placeholder="请输入分享理由" maxlength="50" />
    </i-panel>
    <i-button @click="handleClick" type="warning" :ghost="true" shape="circle" size="small" >我要分享</i-button>
    </view>
    </i-card>



  
<i-card title="哈哈" extra="..." thumb="/static/images/001.png" >
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
    <view slot="footer">不错哦 帽子很喜欢 </view>
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
    <view slot="footer">超喜欢 点赞</view>
</i-card>

<i-card title="哈皮" extra="..." thumb="/static/images/003.png">
    <view slot="content"><image src="/static/images/22.jpg" mode="widthFix"></image></view>
    <view slot="footer">不错哦 点赞</view>
   

</i-card>
<i-card title="23" extra="..." thumb="/static/images/004.png">
    <view slot="content"><image src="/static/images/23.jpg" mode="widthFix"></image></view>
    <view slot="footer">爱了爱了</view>
    <view slot="footer">不错哦 o(￣▽￣)ｄ</view>
</i-card>

<i-card v-for="item in show" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
          <view slot="content">{{item.remark}}</view>
          <view slot="footer">{{item.address}}</view>
 </i-card>




</div>
 
</template>

<script>


export default {
  data () {

    return {
      name:"",
      
      reason:""
    
     
      
      }
   
  },


  methods: {

 changeName (event) {
      this.name = event.mp.detail.detail.value
    },
    changeReason (event) {
      this.reason = event.mp.detail.detail.value
    },
    
    handleClick () {
      if (this.name && this.reason ) {
        wx.showToast({
          title: '分享了' + this.name,
          icon: 'warning',
          duration: 2000
        })
        // TODO:将分享数据提交到云数据库
      } else {
        wx.showToast({
          title: '信息不完整',
          icon: 'none',
          duration: 2000
        })
      }
    }
    
   
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
.tips {
  padding: 20pt;
  font-size: 10pt;
  color:rgb(21, 151, 194);
}

</style>
