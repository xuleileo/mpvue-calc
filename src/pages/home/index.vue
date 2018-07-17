<template>
  <div class="bg">
    <p class="title1">新版个税提高</p>
    <p class="title2">快来算算你能多赚多少钱</p>
    
    <div class="calc">
      <div class="item">
        <i class="item_left">税前金额</i>
        <i class="item_right">元</i>
        <input type="tel" class="money" placeholder="请输入税前金额" v-model="money">
      </div>
      <button type="submit" class="button_calc" @click="btn_calc">计算</button>
    </div>

  </div>
  
</template>

<script>

export default {
  data () {
    return {
      userInfo:"",
      money:"",
    }
  },
  methods: {
    btn_calc(){
      if(this.money <= 0){
        wx.showModal({
          title: '提示',
          content: '税前工资需要大于0',
          duration: 10000
        })
      }else if(this.money > 0 && this.money < 3500){
        wx.showModal({
          title: '提示',
          content: '税改前后您都不需要纳税',
          duration: 10000
        })
      }else{
        const url = '../home_result/main?money='+this.money;
        wx.navigateTo({ url })
      }
    },
    getUserInfo () {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: (res) => {
              console.log("走到这了，获取用户信息");
              this.userInfo = res.userInfo;
              console.log(this.userInfo);
            }
          })
        }
      })
    },
  },

  created () {
    // 调用应用实例的方法获取全局数据
    this.getUserInfo()
  }
}
</script>

<style scoped>
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
.money{
  float: right;
  margin-right: 1vw;
  margin-top: 13px;
  font-size: 16px;
  background: #fff;
  text-align: right;
}
.button_calc{
  width: 60%;
  margin-top: 5vh;
  height: 45px;
  color: #fff;
  background: #62b900;
}
</style>
