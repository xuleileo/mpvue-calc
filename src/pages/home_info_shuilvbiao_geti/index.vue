<template>
  <div class="bg">
    <div class="title">个体工商户的生产、经营所得</div>
    <div class="table">
      <div class="row top">
        <div class="item1">级数</div>
        <div class="item2">全年应纳税所得额</div>
        <div class="item4">税率</div>
        <div class="item5">速算扣除数</div>
      </div>
      <div class="row">
        <div class="item1">1</div>
        <div class="item2">不超过15000元</div>
        <div class="item4">5%</div>
        <div class="item5">0</div>
      </div>
      <div class="row">
        <div class="item1">2</div>
        <div class="item2">超过15000元至30000元的部分</div>
        <div class="item4">10%</div>
        <div class="item5">750</div>
      </div>
      <div class="row">
        <div class="item1">3</div>
        <div class="item2">超过30000元至60000元的部分</div>
        <div class="item4">20%</div>
        <div class="item5">3750</div>
      </div>
      <div class="row">
        <div class="item1">4</div>
        <div class="item2">超过60000元至100000元的部分</div>
        <div class="item4">30%</div>
        <div class="item5">9750</div>
      </div>
      <div class="row">
        <div class="item1">5</div>
        <div class="item2">超过100000元的部分</div>
        <div class="item4">35%</div>
        <div class="item5">14750</div>
      </div>
    </div>
    <div class="title2">计算方式:</div><br>
    <div class="title3">应纳税=应纳税所得额×适用税率-速算扣除数</div>
    
    <button class="button_share" @click="btn_share" open-type="share">普度众好友</button>
    <ad unit-id="adunit-86981e73a17e11f1"></ad>
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
  },
  onShareAppMessage: function (res) {
    if (res.from === 'button') {
      // 来自页面内转发按钮
      console.log(res.target)
    }
    return {
      title: '个税税率一览表',
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
.img{
  width: 100%;
}
.button_share{
  width: 60%;
  margin-top: 5vh;
  height: 45px;
  color: #fff;
  background: #62b900;
}
.table{
  width: 100%;
}
.row{
  width: 100%;
  height: 80rpx;
  display: flex;
  justify-content: space-between;
  align-content: center;
  flex-direction: row;
  font-size: 25rpx;
}
.top{
  border-top: 1rpx solid #333;
}
.item1{
  width: 10%;
  /* border-top: 1rpx solid #333; */
  border-left: 1rpx solid #333;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  /* background: #ff0000; */
}
.item2{
  width: 50%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
}
.item3{
  width: 20%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
}
.item4{
  width: 20%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
}
.item5{
  width: 18%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
}
.jisuanInfo{
  display: flex;
  justify-content: flex-start;
  flex-flow: column;
}
.title2{
  width: 90%;
  margin-top: 50rpx;
  display: inline-flex;
  justify-content: flex-start;
  font-size: 40rpx;
}
.title3{
  width: 92%;
  display: inline-flex;
  justify-content: flex-start;
  font-size: 26rpx;
}
</style>

