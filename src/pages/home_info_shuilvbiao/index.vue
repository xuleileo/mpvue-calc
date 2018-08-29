<template>
  <div class="bg">
    <div class="title">个税税率表</div>
    <div class="calc">
      <div class="item" @click="btn_gongzi">
        <i class="item_left">工资、薪金所得</i>
        <i class="item_right"><img class="array" src="../../../static/assets/arrayRight.png" alt=""></i>
      </div>
      
      <button class="button_share" @click="btn_share" open-type="share">考考好友</button>
    </div>
    
    <ad unit-id="adunit-8c3eb45d6a38e5c6"></ad>
  </div>

  
  
</template>

<script>

export default {
  data () {
    return {
    }
  },
  methods: {
    btn_gongzi(){
      const url = '../home_info_shuilvbiao_gongzi/main';
      wx.navigateTo({ url })
    },
    btn_shuilvbiao(){
      const url = '../home_info_shuilvbiao/main';
      wx.navigateTo({ url })
    },
    btn_fenlei(){
      const url = '../home_info_fenlei/main';
      wx.navigateTo({ url })
    },
    btn_geshui(){
      const url = '../home_info_geshui/main';
      wx.navigateTo({ url })
    },

      
    
  },
  created () {
  },
  onShareAppMessage: function (res) {
    if (res.from === 'button') {
      // 来自页面内转发按钮
      console.log(res.target)
    }
    return {
      title: '99%的人都知道的个税小知识.',
      path: '/pages/home/main'
    }
  }

}
</script>

<style scoped>
ad{
  position: fixed;
  bottom: 0px;
}
.bg{
  text-align: center;
  width: 100vw;
  height: 100vh;
  background: #f2f2f2;
}
.title{
  width: 100%;
  height: 100rpx;
  display: flex;
  justify-content: center;
  align-items: center;
}
.item{
  width: 100vw;
  height: 50px;
  background: #fff;
}
.item_left{
  float: left;
  margin-left: 3vw;
  margin-top: 13px;
  font-size: 16px;
}
.item_right{
  float: right;
  margin-right: 3vw;
  margin-top: 13px;
  font-size: 16px;
}
.item_right .array{
  width: 30rpx;
  height: 40rpx;
}

.top{
  border-top: 1px solid #f2f2f2;
}
.button_share{
  width: 60%;
  margin-top: 5vh;
  height: 45px;
  color: #fff;
  background: #62b900;
}
</style>
