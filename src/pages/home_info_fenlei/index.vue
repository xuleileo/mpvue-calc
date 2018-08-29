<template>
  <div class="bg">
    <div class="title">个人所得税分类</div>
    <i>一、工资、薪金所得；</i>
    <i>二、个体工商户的生产、经营所得；</i>
    <i>三、对企事业单位的承包经营、承租经营所得；</i>
    <i>四、劳务报酬所得；</i>
    <i>五、稿酬所得；</i>
    <i>六、特许权使用费所得；</i>
    <i>七、利息、股息、红利所得；</i>
    <i>八、财产租赁所得；</i>
    <i>九、财产转让所得；</i>
    <i>十、偶然所得；</i>
    <i>十一、经国务院财政部门确定征税的其他所得。</i>
    <button class="button_share" @click="btn_share" open-type="share">同事"啃腚"不知道,不信？</button>
    <ad unit-id="adunit-c823fb2d3afbf62f"></ad>
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
      title: '我知道个税都有哪些分类，你呢？',
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
  /* text-align: center; */
  width: 100vw;
  height: 100vh;
  background: #fff;
}
.title{
  width: 100%;
  height: 150rpx;
  display: flex;
  justify-content: center;
  align-items: center;
}
i{
  padding-left: 20rpx;
  padding-right: 20rpx;
  font-size: 26rpx;
  margin-bottom: 20rpx;
}
.top{
  font-size:30rpx;
  color: #000;
}

.button_share{
  width: 70%;
  margin-top: 5vh;
  height: 45px;
  color: #fff;
  background: #62b900;
}
</style>
