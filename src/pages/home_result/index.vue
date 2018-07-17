<template>
  <div class="bg">
    <p class="title1">计算结果</p>
    <p class="title2">多赚了{{result}}元</p>
    <div class="calc">
      <div class="item">
        <i class="item_left">税改前需纳税</i>
        <i class="item_right">{{money_before}}元</i>
      </div>
      <div class="item">
        <i class="item_left">税改后需纳税</i>
        <i class="item_right">{{money_after}}元</i>
      </div>
      <div class="item">
        <i class="item_left">总计多赚</i>
        <i class="item_right">{{result}}元</i>
      </div>
      <button class="button_share" @click="btn_share" open-type="share">炫耀给好友</button>
    </div>
    

  </div>
  
</template>

<script>

export default {
  data () {
    return {
      result:"",
      money_before:"",
      money_after:"",
    }
  },
  methods: {
    btn_share(){
      wx.showShareMenu({
        withShareTicket: true
      })
    },
    init (money) {
      console.log(money);
      let money_before = money-3500;
      let money_after = money-5000;
      // 税改前需纳税计算
      if(money_before <=0){
        this.money_before = 0;
      }else if(money_before >0 && money_before<=1455){
        this.money_before = (money_before*0.03);
      }else if(money_before>1455 && money_before <=4155){
        this.money_before = (money_before*0.1)-105;
      }else if(money_before>4155 && money_before <=7755){
        this.money_before = (money_before*0.2)-555;
      }else if(money_before>7755 && money_before <= 27255){
        this.money_before = (money_before*0.25)-1005;
      }else if(money_before>27255 && money_before <= 41255){
        this.money_before = (money_before*0.3)-2755;
      }else if(money_before>41255 && money_before <= 57505){
        this.money_before = (money_before*0.35)-5505;
      }else if(money_before>57505){
        this.money_before = (money_before*0.45)-13505;
      }

      // 税改后需纳税计算
      if(money_after<=0){
        this.money_after = 0;
      }else if(money_after > 0 && money_after <=1500){
        this.money_after = money_after * 0.03;
      }else if(money_after > 1500 && money_after <=4500){
        this.money_after = money_after * 0.1 - 105;
      }else if(money_after > 4500 && money_after <=9000){
        this.money_after = money_after * 0.2 - 555;
      }else if(money_after > 9000 && money_after <=35000){
        this.money_after = money_after * 0.25 - 1005;
      }else if(money_after > 35000 && money_after <=55000){
        this.money_after = money_after * 0.3 - 2755;
      }else if(money_after > 55000 && money_after <=80000){
        this.money_after = money_after * 0.35 - 5505;
      }else if(money_after > 80000){
        this.money_after = money_after * 0.45 - 13505;
      }

      this.result = this.money_before - this.money_after;
      



      
    }
  },
  onLoad: function(options) {
    this.init(options.money);
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
      title: '我赚了'+this.result+'元，你赚了多少？',
      path: '/pages/home/main'
    }
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

.button_share{
  width: 60vw;
  margin-left: 20vw;
  margin-top: 5vh;
  height: 45px;
  color: #fff;
  background: #62b900;
}
</style>
