<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>

      <i-panel title="我要推荐">
    <i-input :value="name" @change="changeName($event)" title="店铺名称" autofocus placeholder="名称" maxlength="20"/>
    <i-input :value="address" @change="changeAddress($event)" title="店铺地址" placeholder="地址" maxlength="20" />
    <i-input :value="remark" @change="changeRemark($event)" title="店铺介绍" placeholder="介绍" maxlength="50" />
    <i-button @click="handleClick()">我要推荐</i-button>
    <i-toast id="toast" />
    </i-panel>


<i-card title="我的订单" extra="查看全部订单>" >
    <view slot="content">
    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
    </i-grid>
   </view>
    <view slot="footer"></view>
</i-card>

<i-card title="必备工具" extra="查看全部工具>" >
    <view slot="content">
    <i-grid i-class="no-border">
    <i-grid-item  v-for="po in pos" :key="po" i-class="no-border">
        <i-grid-icon>
            <image :src="po.image" />
        </i-grid-icon>
        <i-grid-label>{{po.title}}</i-grid-label>
    </i-grid-item>
    </i-grid>
   </view>
    <view slot="footer"></view>
</i-card>
 



  </div>
</template>

<script>
const { $Toast } = require('../../../static/dist/base/index');
export default {
  data () {
    return {  
      title_name:"我的订单",
      grids:[
        {title:"待付款",image:"/static/images/11.png"},
        {title:"待收货",image:"/static/images/12.png"},
        {title:"评价",image:"/static/images/13.png"},
        {title:"售后",image:"/static/images/14.png"}
      ],
      pos:[
        {title:"花呗",image:"/static/images/hua.png"},
        {title:"菜鸟驿站",image:"/static/images/cai.png"},
        {title:"客服小蜜",image:"/static/images/ke.png"},
        {title:"主题换肤",image:"/static/images/zhu.png"}
      ],
     
      name: "",
      address: "",
      remark: ""

      
    }
  },

  methods: { 
    goType(type){
      console.log(type)
      let url = '../show/main?type='+type.title
      mpvue.navigateTo({url})

    },
     changeName(event) {
      console.log(event)
      this.name = event.mp.detail.detail.value
    },
    changeAddress(event) {
      console.log(event)
      this.address = event.mp.detail.detail.value
    },
    changeRemark(event) {
      console.log(event)
      this.remark = event.mp.detail.detail.value
    },
    handleClick() {
      if (this.name && this.address && this.remark) {
        let event = {
          name: this.name,
          address: this.address,
          remark: this.remark,
          image: 'cloud://edu-868a10.6564-edu-868a10/food/4.png'
        }
        wx.cloud.callFunction({ name: 'new_shop', data: event }).then(
              res => {
                console.log(res)
                }
        )
        $Toast({
            content: '数据已经提交',
            type: 'success'
        });
      } else {
        $Toast({
            content: '请填写完整信息',
            type: 'warning'
        });
      }
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
