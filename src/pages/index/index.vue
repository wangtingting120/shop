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


<i-divider color="#ed3f14" lineColor="#ed3f14">加载已经完成,没有其他数据</i-divider>


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
      bo:[
        {image:"/static/images/ku1.jpg",name:"裤子",price:"100元"},
        {image:"/static/images/wai1.jpg",name:"外套",price:"100元"},
        {image:"/static/images/ku2.jpg",name:"裤子",price:"120元"},
        {image:"/static/images/mao2.jpg",name:"帽子",price:"65元"},
        {image:"/static/images/xie1.jpg",name:"鞋子",price:"100元"},
        {image:"/static/images/wai2.jpg",name:"外套",price:"1250元"},
        {image:"/static/images/xie2.jpg",name:"鞋子",price:"120元"},
        {image:"/static/images/mao1.jpg",name:"帽子",price:"50元"}
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
