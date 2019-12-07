
<template>
  <div>
    <i-panel :title="title_name">
    <scroll-view scroll-y>
      <view v-for="item in bo" :key="item" class="product" >
        <image :src="item.image" mode="widthFix"/>
        <view class="info">
          <text>{{item.name}}</text>
          <text class="price">{{item.price}}</text>
      </view>
      <checkbox-group :id="item.id" bindchange="checkboxChange">
        <checkbox :value="item.id"></checkbox>
      </checkbox-group>
      </view>
    </scroll-view>


    
    <view class="bottom">
      <button>
        去付款
        <text>￥{{price}}</text>
      </button>
    </view>

    </i-panel>




</div>
 
</template>

<script>


export default {
  data () {
  

    return {
     title_name:"我的购物车",   
    bo:[
        {name:"牛仔裤",image:"/static/images/-1.jpg",id:"1",price:"100"},
        {name:"百褶裙",image:"/static/images/-2.jpg",id:"2",price:"10"},
        {name:"毛茸茸的帽子",image:"/static/images/-3.jpg",id:"3",price:"200"},
        {name:"超厚的外套",image:"/static/images/-4.jpg",id:"4",price:"60"}
      ],
      
  price:0
     
      
      }
    
   
  },

  methods: {

   checkboxChange(e){
      var sumPrice = 0 ;
      var id= e.currentTarget.id;
      var num = e.detail.value;
      var p = this.data.bo;
      if(num !=''){
        for(var i=0;i<p.length;i++){
          if(p[i].id ==id){
          
              sumPrice = this.data.price+p[i].price
           
          }
        }

      }else{
        for( var i=0;i<p.length;i++){
          if(p[i].id == id){
           sumPrice =  this.data.price-p[i].price
          }
            }
          }
          console.log(sumPrice)
          this.setData({
            price:sumPrice
          })
        }
      
    


    
   
    },

  created () {
 
  }
}
</script>

<style scoped>
scroll-view{
  width:100%;
  height:100vh;
}
.product{
  width:100%;
  display: flex;
  flex-direction:row;
  justify-content:space-around;
  align-items: center;
  border-bottom:1px solid #aa3406;
}
.product image{
  width: 200rpx;
}
.info{
  width:80%;
  display: flex;
  flex-direction: column;
}
.price{
  color:red;
  font-weight: 600;
}
.bottom{
  width:100%;
  position: absolute;
  bottom:0;
  left:0;
}
</style>

