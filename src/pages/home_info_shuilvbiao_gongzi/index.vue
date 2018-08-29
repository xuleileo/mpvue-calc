<template>
  <div class="bg">
    <div class="title">工资薪金所得</div>
    <div class="table">
      <div class="row top">
        <div class="item1">级数</div>
        <div class="item2">全月应纳税所得额</div>
        <div class="item3">全月应纳税所得额</div>
        <div class="item4">税率</div>
        <div class="item5">速算扣除数</div>
      </div>
      <div class="row">
        <div class="item1">1</div>
        <div class="item2">不超过1500元</div>
        <div class="item3">不超过1455元的</div>
        <div class="item4">3%</div>
        <div class="item5">0</div>
      </div>
      <div class="row">
        <div class="item1">2</div>
        <div class="item2">超过1500元至4500元的部分</div>
        <div class="item3">超过1455元至7755元的部分</div>
        <div class="item4">10%</div>
        <div class="item5">105</div>
      </div>
      <div class="row">
        <div class="item1">3</div>
        <div class="item2">超过4500元至9000元的部分</div>
        <div class="item3">超过4155元至7755元的部分</div>
        <div class="item4">20%</div>
        <div class="item5">555</div>
      </div>
      <div class="row">
        <div class="item1">4</div>
        <div class="item2">超过9000元至35000元的部分</div>
        <div class="item3">超过7755元至27255元的部分</div>
        <div class="item4">25%</div>
        <div class="item5">1005</div>
      </div>
      <div class="row">
        <div class="item1">5</div>
        <div class="item2">超过35000元至55000元的部分</div>
        <div class="item3">超过27255元至41255元的部分</div>
        <div class="item4">30%</div>
        <div class="item5">2775</div>
      </div>
      <div class="row">
        <div class="item1">6</div>
        <div class="item2">超过55000元至80000元的部分</div>
        <div class="item3">超过41255元至57505元的部分</div>
        <div class="item4">35%</div>
        <div class="item5">5505</div>
      </div>
      <div class="row">
        <div class="item1">7</div>
        <div class="item2">超过80000元的部分</div>
        <div class="item3">超过57505元的部分</div>
        <div class="item4">45%</div>
        <div class="item5">13505</div>
      </div>
    </div>
    <div class="title2">计算方式:</div><br>
    <div class="title3">应纳个人所得税税额=应纳税所得额×适用税率-速算扣除数</div>
    
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
  width: 30%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
}
.item3{
  width: 30%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1rpx solid #333;
  border-right: 1rpx solid #333;
}
.item4{
  width: 12%;
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

