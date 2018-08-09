<template>
  <div>
    <div class="header">
      <img src="//y.gtimg.cn/mediastyle/yqq/img/logo@2x.png?nowebp=1 2x" alt="" class="qqlogo">
      <span class="header-title">音乐播放器</span>
    </div>
    <div class="footer">
      <ul class="footer-title">
        <li @click="routerLink('/')" ><span  class="title-left" :class="{classa:flag}">推荐</span></li>
        <li @click="routerLink('list')"><span  class="title-right" :class="{classb:!flag}">排行榜</span></li>
      </ul>
      <div :class="{classA:flag}"></div>
      <div :class="{classB:!flag}"></div>
    </div>
  </div>
</template>

<script>

export default({

  data(){
      return{
      flag:true
      }
  },
  methods:{
    routerLink(path){
      this.flag = !this.flag;
        this.$router.push(path);
    },


  }

})

</script>


<style scoped>
  .header{
    background: #0fff;
    height:50px;
    position: fixed;
    top:0;
    left: 0;
    width:100%;
    color: white;
    color: #000;
  }
  .footer{
    height:50px;
    position: fixed;
    top:50px;
    left: 0;
    width:100%;
  }
  .header-title{
    text-align: center;
    position: absolute;
    left: 50%;
    transform: translate(-50%,50%);
  }
  .footer-title{
    display: flex;
  }
  .footer-title li{
    flex:1;
    text-align: center;
    line-height: 50px;

  }
  .qqlogo{
    width: 80px;
    height: 20px;
    position: absolute;
    top:50%;
    transform:translate(50%,-50%);
  }
  .classA{
    height: 4px;
    width:50%;
    background: green;
    position: absolute;
  }
  .classB{
    height: 4px;
    width:50%;
    background: green;
    position: absolute;
    right: 0;
  }
  .classa{
    color: green;
  }
  .classb{
    color: green;
  }
</style>
