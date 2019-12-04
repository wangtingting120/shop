<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>

   
    
    <i-panel :title="title_name">
    <view style="padding: 15px;">
<i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
    </i-grid>
     
    </view>
</i-panel>
 



  </div>
</template>

<script>

export default {
  data () {
    return {  
      title_name:"我的订单",
      grids:[
        {title:"待付款",image:"/static/images/11.png"},
        {title:"待收货",image:"/static/images/12.png"},
        {title:"评价",image:"/static/images/13.png"},
        {title:"退款/售后",image:"/static/images/14.png"}
      ],
      
    }
  },

  methods: { 
    goType(type){
      console.log(type)
      let url = '../list/main?type='+type.title
      mpvue.navigateTo({url})

    }
 
  },

  created () {
  }
}
</script>

<style scoped>
.userinfo {
  position: relative;
  width: 750rpx;
  height: 320rpx;
  color: #666;
  display: flex;
  flex-direction: column;
  align-items: center;
}
 
.userinfo-avatar {
  overflow:hidden;
  display: block;
  width: 160rpx;
  height: 160rpx;
  margin: 20rpx;
  margin-top: 50rpx;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}
div >>> .no-border{
  border-width:0pt;
}
div >>> .split{
  margin-bottom:10pt;
}

</style>
