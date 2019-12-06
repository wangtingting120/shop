<template>
  <div>
    <i-panel class="search">
    <input type="text" confirm-type="search" placeholder="请搜索喜欢的商品">
   </i-panel>
   
   <swiper 
    :indicator-dots="indicatorDots"
    :autoplay="autoplay"
    :interval="interval"
    :duration="duration"
    :circular="circular"
    
    >
    <block v-for="img in imgUrls" :key="img">
      <swiper-item>
        <image :src="img" style="width:100%"/>
      </swiper-item>
      </block>
      </swiper>
    
    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
    </i-grid>

<i-panel :title="title_name">
    <view style="padding: 15px;">

        <i-card v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
        </i-card>
    </view>
</i-panel>

<i-panel :title="title_name">
  <view class="wrap">
    <view class="product">
       <image src="/static/images/21.jpg" mode="widthFix" ></image>
       <view class="info">
         <text class="name">仙女裙</text>
         <text class="price">100</text>
       </view>
   </view>
     <view class="product">
       <image src="/static/images/21.jpg" mode="widthFix" ></image>
       <view class="info">
         <text class="name">仙女裙</text>
         <text class="price">100</text>
       </view>
   </view>
        <view class="product">
       <image src="/static/images/21.jpg" mode="widthFix" ></image>
       <view class="info">
         <text class="name">仙女裙</text>
         <text class="price">100</text>
       </view>
   </view>
        <view class="product">
       <image src="/static/images/21.jpg" mode="widthFix" ></image>
       <view class="info">
         <text class="name">仙女裙</text>
         <text class="price">100</text>
       </view>
   </view>
     
   </view>

</i-panel>



</div>
 
</template>

<script>


export default {
  data () {
    return {
      title_name:"热门",
      grids:[
        {title:"外套",image:"/static/images/1.png"},
        {title:"帽子",image:"/static/images/2.png"},
        {title:"裤子",image:"/static/images/3.png"},
        {title:"鞋子",image:"/static/images/4.png"}
      ],
      top:[
        {name:"店铺1",address:"地址1",image:"/static/images/xu.jpg",remark:"介绍1"},
        {name:"店铺2",address:"地址2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍2"},
        {name:"店铺3",address:"地址3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍3"},
        {name:"店铺4",address:"地址4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍4"}



      ],
      imgUrls:[
        'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
        'https://images.unsplash.com/photo-1551214012-84f95e060dee?w=640',
        'https://images.unsplash.com/photo-1551446591-142875a901a1?w=640'

      ],
      indicatorDots: false,
      autoplay: false,
      interval: 5000,
      duration: 1000

      
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
div >>> .no-border{
  border-width:0pt;
}
div >>> .split{
  margin-bottom:10pt;
}
.search{
  display:flex;
  height:60rpx;
  border:1px solid rgb(235, 129, 29);
  padding-left:20rpx;
  color:#6666;
  border-radius:30rpx;
  margin:10rpx 0;
  font-size:22rpx;
  background-color: white;
}
.wrap{
  background-color: rgba(187, 20, 20, 0.4);
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.wrap .product{
  display:flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width:46%;
  margin:6rpx 10rpx;
  background-color: rgba(12, 10, 31, 0.4);
  border-bottom-left-radius: 16rpx;
  border-bottom-right-radius: 16rpx;
}
.product image{
  width:100%;
  border-top-left-radius: 16rpx;
  border-top-right-radius: 16rpx;
}
.info{
  display: flex;
  flex-direction: row;
  justify-content:space-around; 


}
.name{
  color:white;
}
.info .price{
  color:red;
}
</style>
