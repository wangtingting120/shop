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
        <image :src="img"/>
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
  <view class="wrap">
    <view v-for="item in bo" :key="item" class="product">
       <image :src="item.image" style="width:100%"/>
       <view class="info">
         <text class="name">{{item.name}}</text>
         <text class="price">{{item.price}}</text>
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
      title_name:"--------------------热门----------------------",
      grids:[
        {title:"外套",image:"/static/images/1.png"},
        {title:"帽子",image:"/static/images/2.png"},
        {title:"裤子",image:"/static/images/3.png"},
        {title:"鞋子",image:"/static/images/4.png"}
      ],
      bo:[
        {image:"/static/images/ku1.jpg",name:"哈伦裤",price:"￥100元"},
        {image:"/static/images/wai1.jpg",name:"毛领外套",price:"￥100元"},
        {image:"/static/images/ku2.jpg",name:"老爹裤",price:"￥120元"},
        {image:"/static/images/mao2.jpg",name:"贝雷帽",price:"￥65元"},
        {image:"/static/images/xie1.jpg",name:"小白鞋",price:"￥100元"},
        {image:"/static/images/wai2.jpg",name:"风衣外套",price:"￥1250元"},
        {image:"/static/images/xie2.jpg",name:"马丁靴",price:"￥120元"},
        {image:"/static/images/mao1.jpg",name:"针织帽",price:"￥50元"}
      ],
      imgUrls:[
        '/static/images/h1.jpg',
        '/static/images/h2.jpg',
        '/static/images/h5.jpg',
        '/static/images/h4.jpg'
        

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
  height:65rpx;
  border:1px solid  rgba(11, 54, 65, 0.4);
  padding-left:20rpx;
  color:#6666;
  border-radius:40rpx;
  margin:10rpx 0;
  font-size:22rpx;
  background-color: white;
}
.wrap{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.wrap .product{
  display:flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width:45%;
  margin:10px auto;
  background-color: rgba(11, 54, 65, 0.4);
  border-radius: 10px;
  box-shadow: 2px 2px 10px #888888;
}
.product image{
  width:80%;
  border-top-left-radius: 16rpx;
  border-top-right-radius: 16rpx;
  height: 180px;

}
.info{
  display: flex;
  flex-direction: row;
  justify-content:space-around; 


}
.name{
  color:white;
  size: 10;
}
.info .price{
  color:rgba(255, 0, 0, 0.521);
}
</style>
