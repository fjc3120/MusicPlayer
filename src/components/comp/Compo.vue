<template>
  <div>
    <div class="header">
      <span class="header-title">音乐播放器</span>
    </div>
    <div class="footer">
      <ul class="footer-title">
        <li @click="routerLink('/')"><span  class="title-left">推荐</span></li>
        <li @click="routerLink('list')"><span  class="title-right">排行榜</span></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default({
  methods:{
    routerLink(path){
        this.$router.push(path);
    }
  }
})

</script>


<style scoped>
  .header{
    background: #0000ff;
    height:50px;
    position: fixed;
    top:0;
    left: 0;
    width:100%;
    color: white;
  }
  .footer{
    background: #0fff;
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

</style>
