<template>
  <div>
    <div class="top">
      <swipe class="my-swipe">
        <swipe-item class="slide1"><img src="@/assets/img/1.jpg" alt=""></swipe-item>
        <swipe-item class="slide2"><img src="@/assets/img/2.jpg" alt=""></swipe-item>
        <swipe-item class="slide3"><img src="@/assets/img/3.jpg" alt=""></swipe-item>
        <swipe-item class="slide3"><img src="@/assets/img/4.jpg" alt=""></swipe-item>
        <swipe-item class="slide3"><img src="@/assets/img/5.jpg" alt=""></swipe-item>
      </swipe>
    </div>
    <div>
      <aplayer v-if="isReady" :music= 'music' :list= 'musiclist' :showLrc = 'true' />
    </div>
  </div>

</template>

<script>
  require('vue-swipe/dist/vue-swipe.css');
  import Aplayer from 'vue-aplayer'
  import axios from 'axios'
  import { Swipe, SwipeItem } from 'vue-swipe';
  export default({
  data(){
      return{
        music:{},
        musiclist:[],
        isReady:false
      }
  },
    components:{
      Aplayer,
      'swipe': Swipe,
      'swipe-item': SwipeItem
    },
    created(){
      this.getData();
    },
    methods:{
        getData(){
            axios.get('./static/data/musicdata.json')
              .then((res)=>{
                for(let i=0;i<res.data.musicData.length;i++){
                  this.musiclist.push({
                    title : res.data.musicData[i].title,
                    artist : res.data.musicData[i].artist,
                    src :res.data.musicData[i].src,
                    pic : res.data.musicData[i].pic,
                   lrc: 'http://localhost:8081/static/'+res.data.musicData[i].lrc,
                  })
                }
                let thisObj = {};
                thisObj.title = res.data.musicData[0].title;
                thisObj.artist = res.data.musicData[0].artist;
                thisObj.src = res.data.musicData[0].src;
                thisObj.pic = res.data.musicData[0].pic;
                thisObj.lrc= 'http://localhost:8081/static/'+res.data.musicData[0].lrc;
                this.music = thisObj;
                this.isReady = true;
              })
              .catch((error)=>{
                console.log(error);
              });
        }
    }
  })

</script>


<style scoped>
.top{
  width:100%;
  height: 200px;

}
.my-swipe {
  height: 100%;
  width: 100%;
  font-size: 30px;
  text-align: center;
}
.my-swipe img{
  height: 100%;
  width: 100%;
}
</style>
