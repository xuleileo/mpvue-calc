<template>
  <div class="bg">
    <p class="title1">10月1日起实施新版个税5000元起征</p>
    <p class="title2">快来算算你能多赚多少钱</p>
    
    <div class="calc">
      <div class="item">
        <i class="item_left">税前金额</i>
        <input type="tel" class="money" placeholder="请输入税前金额" v-model="money">
      </div>
      <div class="item">
        <i class="item_left">五险一金</i>
        <input type="tel" class="money" placeholder="请输入五险一金金额" v-model="money2">
      </div>
      <button type="submit" class="button_calc" @click="btn_calc">计算</button>
      <div class="item bonus" @click="btn_bonus">
        <i class="item_left" >年终奖计算</i>
      </div>
      <div class="item bonus" @click="btn_info">
        <i class="item_left" >个税介绍</i>
      </div>
      <ad unit-id="adunit-f5c8584430a94aa2"></ad>
    </div>

  </div>
  
</template>

<script>

export default {
  data () {
    return {
      userInfo:"",
      money:"",
      money2:""
    }
  },
  methods: {
    btn_info(){
      const url = '../home_info/main';
      wx.navigateTo({ url })
    },
    btn_bonus(){
      const url = '../home_bonus/main';
      wx.navigateTo({ url })
    },
    btn_calc(){
      if(this.money <= 0){
        wx.showModal({
          title: '提示',
          content: '税前工资需要大于0',
          duration: 10000
        })
      }else{
        const url = '../home_result/main?money='+(this.money-this.money2);
        wx.navigateTo({ url })
      }
    },
    getUserInfo () {
      // 调用登录接口
      // wx.login({
      //   success: () => {
      //     wx.getUserInfo({
      //       success: (res) => {
      //         console.log("走到这了，获取用户信息");
      //         this.userInfo = res.userInfo;
      //         console.log(this.userInfo);
      //       }
      //     })
      //   }
      // })
    },
  },

  created () {
    
      // wx.navigateToMiniProgram({
      //   appId: "wx04de860284c78cd9",
      //   path: '/pages/home/main'
      //   }
      // )
    // 调用应用实例的方法获取全局数据
    // this.getUserInfo()
  }
}
</script>

<style scoped>
ad{
  position: fixed;
  bottom: 0px;;
}
.bg{
  text-align: center;
  width: 100vw;
  height: 100vh;
  background: #f2f2f2;
}
.title1{
  padding-top: 3vh;
}
.title2{
  margin-top: 3vh;
}
.calc{
  margin-top: 10vh;
}
.item{
  width: 100vw;
  height: 100rpx;
  background: #fff;
}
.item_left{
  float: left;
  margin-left: 3vw;
  margin-top: 22rpx;
  font-size: 16px;
}
.money{
  width: 50vw;
  float: right;
  margin-right: 3vw;
  margin-top: 24rpx;
  font-size: 16px;
  background: #fff;
  text-align: right;
}
.bonus{
  margin-top: 20rpx;;
}
.button_calc{
  width: 60%;
  margin-top: 5vh;
  height: 45px;
  color: #fff;
  background: #62b900;
}
</style>
