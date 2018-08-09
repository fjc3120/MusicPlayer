<template>
<div>
  <swipe class="my-swipe">
    <swipe-item class="slide1"><img src="@/assets/img/1.jpg" alt=""></swipe-item>
    <swipe-item class="slide2"><img src="@/assets/img/2.jpg" alt=""></swipe-item>
    <swipe-item class="slide3"><img src="@/assets/img/3.jpg" alt=""></swipe-item>
    <swipe-item class="slide3"><img src="@/assets/img/4.jpg" alt=""></swipe-item>
    <swipe-item class="slide3"><img src="@/assets/img/5.jpg" alt=""></swipe-item>
  </swipe>
  <div><img src="@/assets/img/f.png" alt=""></div>
  <hr>
  <div class="dt">歌单推荐 </div>
  <hr>
  <div class="box">
    <ul>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo/radio/track_radio_307_13_1.jpg?max_age=2592000" alt=""><span>123456789</span></div></li>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo/radio/track_radio_199_13_1.jpg?max_age=2592000" alt=""><span>123456789</span></div></li>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo_new/T006R300x300M00000333So02drvak.jpg?max_age=2592000" alt=""><span>123456789</span></div></li>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo_new/T006R300x300M0000013j8zs1jRnLQ.jpg?max_age=2592000" alt=""><span>123456789</span></div></li>
    </ul>
  </div>
</div>
</template>

<script>
  require('vue-swipe/dist/vue-swipe.css');
  import { Swipe, SwipeItem } from 'vue-swipe';
  export default({
    components: {
      'swipe': Swipe,
      'swipe-item': SwipeItem
    },
    methods: {
      routerLink(path){
        this.$router.push(path);
      }
    }
//    methods:{
//        getData(){
//            axios.get('https://bird.ioliu.cn/netease?url=http://s.plcloud.music.qq.com/fcgi-bin/fcg_yqq_song_detail_info.fcg?songmid={$SongMid}')
//              .then(function (response) {
//                console.log(response);
//              })
//              .catch(function (error) {
//                console.log(error);
//              });
//        }
//    },
//    created(){
//      getData();
//    }
  })

</script>


<style scoped>

  .my-swipe {
    height: 140px;
    width: 100%;
    font-size: 30px;
    text-align: center;
  }
  .my-swipe img{
    height: 100%;
    width: 100%;
  }
  .dt{
    border-left: 3px solid red;
  }
  .box{
    width:100%;
  }
  .box ul{
    width:100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }
  .box li{
    width:40%;
    margin: 10px 10px 10px 10px;
  }
</style>
