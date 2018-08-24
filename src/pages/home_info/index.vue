<template>
  <div class="bg">
    <div class="title">个税介绍</div>
    <div class="calc">
      <div class="item" @click="btn_geshui">
        <i class="item_left">个税税法</i>
        <i class="item_right"><img class="array" src="../../../static/assets/arrayRight.png" alt=""></i>
      </div>
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
    btn_geshui(){
      const url = '../home_info_geshui/main';
      wx.navigateTo({ url })
    },

      
    
  },
  created () {
  },

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

</style>
