<template>
<div class="BBox">
  <swipe class="my-swipe">
    <swipe-item class="slide1"><img src="@/assets/img/top1.jpg" alt=""></swipe-item>
    <swipe-item class="slide2"><img src="@/assets/img/top2.jpg" alt=""></swipe-item>
    <swipe-item class="slide3"><img src="@/assets/img/top3.jpg" alt=""></swipe-item>
    <swipe-item class="slide3"><img src="@/assets/img/top4.jpg" alt=""></swipe-item>
    <swipe-item class="slide3"><img src="@/assets/img/top5.jpg" alt=""></swipe-item>
  </swipe>
  <div><img src="@/assets/img/f.png" alt=""></div>
  <hr>
  <div class="dt">歌单推荐 </div>
  <hr>
  <div class="box">
    <ul>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo/radio/track_radio_307_13_1.jpg?max_age=2592000" alt=""><span>古风</span></div></li>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo/radio/track_radio_199_13_1.jpg?max_age=2592000" alt=""><span>激情</span></div></li>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo_new/T006R300x300M00000333So02drvak.jpg?max_age=2592000" alt=""><span>流行</span></div></li>
      <li @click="routerLink('music')"><div><img src="https://y.gtimg.cn/music/photo_new/T006R300x300M0000013j8zs1jRnLQ.jpg?max_age=2592000" alt=""><span>民族</span></div></li>
    </ul>
  </div>
</div>
</template>

<script>
  require('vue-swipe/dist/vue-swipe.css');
  import axios from 'axios';
  import { Swipe, SwipeItem } from 'vue-swipe';
  export default({

    created(){
      this.getData();
    },
    components: {
      'swipe': Swipe,
      'swipe-item': SwipeItem
    },
    methods: {
      routerLink(path){
        this.$router.push(path);
      },
      getData(){
        axios.get('https://bird.ioliu.cn/v2?url=https://c.y.qq.com/v8/fcg-bin/fcg_v8_toplist_cp.fcg?g_tk=5381&uin=0&format=json&inCharset=utf-8&outCharset=utf-8&notice=0&platform=h5&needNewCode=1&tpl=3&page=detail&type=top&topid=4&_=1533965436259')
          .then(function (response) {
            console.log(response);
          })
          .catch(function (error) {
            console.log(error);
          });
      }
    },

  })

</script>


<style scoped>
  .BBox{
    background: rgba(0,0,0,0.2);
  }
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
    /*width:100%;*/
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    /*margin:10px 10px 10px 10px ;*/
  }
  .box li{
    width:40%;
    margin: 10px 10px 10px 10px;
    background: white;
  }
</style>
