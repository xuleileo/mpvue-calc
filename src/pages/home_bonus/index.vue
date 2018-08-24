<template>
  <div class="bg">
    <div class="item top">
      <i class="left">我的年终奖:</i>
      <input placeholder="请输入您的年终奖" type="number" class="money" v-model="money" @input="change1">
    </div>

    <div class="item">
      <i class="left">平均每个月</i>
      <i class="money">{{monthMoney}}</i>
    </div>
    <div class="item bo">
      <i class="left">纳税比例</i>
      <i class="money">{{bili}}</i>
    </div>
    <div class="item bo">
      <i class="left">应纳税款</i>
      <i class="money">{{shui}}</i>
    </div>
    <div class="item bo">
      <i class="left">税后收入</i>
      <i class="money">{{shuihou}}</i>
    </div>

    <button class="button_share" @click="btn_share" open-type="share">分享给好友</button>
    <ad unit-id="adunit-8b1b8bc1e86ba63e"></ad>

  </div>

  
  
</template>

<script>

export default {
  data () {
    return {
      money:"",
      bili:"",
      monthMoney:"",
      shui:"",
      shuihou:"",
    }
  },
  methods: {

    change1(){
      if(1){
        this.monthMoney = (this.money/12).toFixed(2);
      }
      if(this.monthMoney<=1500){
        this.bili = "3%";
        this.shui = (this.money*0.03).toFixed(2);
      }else if(this.monthMoney > 1500 && this.monthMoney <= 4500){
        this.bili = "10%";
        this.shui = ((this.money)*0.1 - 105).toFixed(2);
      }else if(this.monthMoney > 4500 && this.monthMoney <= 9000){
        this.bili = "20%";
        this.shui = ((this.money - 4500)*0.2 - 555).toFixed(2);
      }else if(this.monthMoney > 9000 && this.monthMoney <= 35000){
        this.bili = "25%";
        this.shui = ((this.money)*0.25 - 1005).toFixed(2);
      }else if(this.monthMoney > 35000 && this.monthMoney <= 55000){
        this.bili = "30%";
        this.shui = ((this.money)*0.30 - 2755).toFixed(2);
      }else if(this.monthMoney > 55000 && this.monthMoney <= 80000){
        this.bili = "35%";
        this.shui = ((this.money)*0.35 - 5505).toFixed(2);
      }else if(this.monthMoney > 80000){
        this.bili = "45%";
        this.shui = ((this.money)*0.45 - 13505).toFixed(2);
      }

      this.shuihou = (this.money - this.shui).toFixed(2);

      
    },

      
    
  },
  created () {
  },
  onShareAppMessage: function (res) {
    console.log("走到分享了");
    if (res.from === 'button') {
      // 来自页面内转发按钮
      console.log(res.target)
    }
    return {
      title: '我的年终奖是'+this.money+'元，你的呢？',
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
.left{
  margin-left: 30rpx;
}
.top{
  margin-bottom: 50rpx;
}
.item{
  position: relative;
  width: 100vw;
  height: 80rpx;
  background: #fff;
  top: 100rpx;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.bo{
  border-top:1px solid #f2f2f2;
}
.money{
  margin-right: 30rpx;
  /* background: #f2f2f2; */
  text-align: right;
}
.button_share{
  width: 60vw;
  margin-left: 20vw;
  margin-top: 200rpx;
  height: 45px;
  color: #fff;
  background: #62b900;
}

</style>
