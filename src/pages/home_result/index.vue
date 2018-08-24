<template>
  <div class="bg">
    <p class="title1">个税从3500元调整到5000元起征</p>
    <p class="title2">我竟然多赚了{{result}}元</p>
    <p class="title3">{{msg}}</p>
    <div class="calc">
      <div class="item">
        <i class="item_left">税改前实发工资</i>
        <i class="item_right">{{money_before_money}}元</i>
      </div>
      <div class="item">
        <i class="item_left">税改前需纳税</i>
        <i class="item_right">{{money_before}}元</i>
      </div>
      <div class="item">
        <i class="item_left">税改后实发工资</i>
        <i class="item_right">{{money_after_money}}元</i>
      </div>
      <div class="item">
        <i class="item_left">税改后需纳税</i>
        <i class="item_right">{{money_after}}元</i>
      </div>
      
      <div class="item">
        <i class="item_left">总计多赚</i>
        <i class="item_right">{{result}}元</i>
      </div>
      <div class="item">
        <i class="item_left">增加霸气值</i>
        <input type="tel" class="money_input" v-model="msg">
      </div>
      <button class="button_share" @click="btn_share" open-type="share">炫耀给好友</button>
      <ad unit-id="adunit-b2a012ab5ff4c408"></ad>
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
      money_before_money:"",
      money_after_money:"",
      msg : "哈哈羡慕不羡慕",
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
      }else if(money_before >0 && money_before<=1500){
        this.money_before = parseInt(money_before*0.03);
      }else if(money_before>1500 && money_before <=4500){
        this.money_before = parseInt(money_before*0.1)-105;
      }else if(money_before>4500 && money_before <=9000){
        this.money_before = parseInt(money_before*0.2)-555;
      }else if(money_before>9000 && money_before <= 35000){
        this.money_before = parseInt(money_before*0.25)-1005;
      }else if(money_before>35000 && money_before <= 55000){
        this.money_before = parseInt(money_before*0.3)-2755;
      }else if(money_before>55000 && money_before <= 80000){
        this.money_before = parseInt(money_before*0.35)-5505;
      }else if(money_before>80000){
        this.money_before = parseInt(money_before*0.45)-13505;
      }
      this.money_before_money = money-this.money_before;

      // 税改后需纳税计算
      if(money_after<=0){
        this.money_after = 0;
      }else if(money_after > 0 && money_after <=1500){
        this.money_after = parseInt(money_after * 0.03);
      }else if(money_after > 1500 && money_after <=4500){
        this.money_after = parseInt(money_after * 0.1) - 105;
      }else if(money_after > 4500 && money_after <=9000){
        this.money_after = parseInt(money_after * 0.2) - 555;
      }else if(money_after > 9000 && money_after <=35000){
        this.money_after = parseInt(money_after * 0.25) - 1005;
      }else if(money_after > 35000 && money_after <=55000){
        this.money_after = parseInt(money_after * 0.3) - 2755;
      }else if(money_after > 55000 && money_after <=80000){
        this.money_after = parseInt(money_after * 0.35) - 5505;
      }else if(money_after > 80000){
        this.money_after = parseInt(money_after * 0.45) - 13505;
      }

      this.money_after_money = money - this.money_after;

      this.result = parseInt(this.money_before - this.money_after);
      let num = parseInt(Math.random()*10);
      if(this.result <=0){
        switch(num){
          case 0:
            this.msg ="羡慕吧，来咬我呀！";
          break;
          case 1:
            this.msg ="纳尼？个税是什么？能吃吗？";
          break;
          case 2:
            this.msg ="纳税是不可能的，这辈子都不可能";
          break;
          case 3:
            this.msg ="有这么好的老板，我怎么可能纳税";
          break;
          case 4:
            this.msg ="老板，请问您想说点什么";
          break;
          case 5:
            this.msg ="老板!我要纳税！我要纳税！我要纳税！";
          break;
          case 6:
            this.msg ="请问此时我的心里阴影面积是多少";
          break;
          case 7:
            this.msg ="这么大的秘密，千万不要告诉任何人";
          break;
          case 8:
            this.msg ="吐血，调不调整我都不用纳税";
          break;
          case 9:
            this.msg ="我什么时候能纳税呀~";
          break;
        }
      }else if(this.result > 0){
        switch(num){
          case 0:
            this.msg ="山不厌高，海不厌深";
          break;
          case 1:
            this.msg ="这点钱！也就够我一顿早饭钱！";
          break;
          case 2:
            this.msg ="每顿泡面都可以加个蛋了！";
          break;
          case 3:
            this.msg ="还有比我少的吗？来比比呀！";
          break;
          case 4:
            this.msg ="还有比我多的吗？来比比呀！";
          break;
          case 5:
            this.msg ="老板!我要多纳税！";
          break;
          case 6:
            this.msg ="钱是什么，我会在乎吗";
          break;
          case 7:
            this.msg ="这么大的秘密，千万不要告诉别人";
          break;
          case 8:
            this.msg ="这是哪里，我走丢了，这是什么钱";
          break;
          case 9:
            this.msg ="曾经有一份纳税0元的工作我没有珍惜~";
          break;
      }
    }



      
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
.title3{
  margin-top: 3vh;
}
.calc{
  margin-top: 5vh;
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
.money_input{
  width: 60vw;
  float: right;
  margin-right: 3vw;
  margin-top: 23rpx;
  font-size: 16px;
  background: #fff;
  text-align: right;
}
</style>
