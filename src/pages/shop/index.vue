
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
        <checkbox-group :id="item.id">
          <checkbox @click="checkboxChange"></checkbox>
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
     title_name:"",
     bo:[
        {name:"牛仔裤",image:"/static/images/-1.jpg",id:"1",price:"￥100"},
        {name:"百褶裙",image:"/static/images/-2.jpg",id:"2",price:"￥100"},
        {name:"毛茸茸的帽子",image:"/static/images/-3.jpg",id:"3",price:"￥20"},
        {name:"超厚的外套",image:"/static/images/-4.jpg",id:"4",price:"￥60"}
      ],
      value:false,
      price:0
      }
    
   
  },

  methods: {

   checkboxChange(){
    //  console.log(this.price)
    //  console.log(this.bo)
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
  display: flex;
  flex-direction:row;
  justify-content:space-around;
  align-items: center;
  border-bottom:1px solid lightgray;
  margin: 20px;
}
.product image{
  width: 200rpx;
  border-radius: 5px;
  margin: 10px;

}
.info{
  width:80%;
  display: flex;
  flex-direction: column;
  margin-left: 20px;
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

