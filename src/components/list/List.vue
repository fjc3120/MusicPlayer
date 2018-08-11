<template>
  <div>
    <div>
      <ul>
        <li v-for="(item,index) in photos" :key="index" class="list" @click="routerLink('music')">
          <div>
            <img :src="item.picUrl" alt="">
            <h3>{{ item.topTitle }}</h3>
            <p>{{ item.songList[0].songname }}--{{ item.songList[0].singername }}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'
  export default({
    data(){
        return{
          photos:[],

        }
    },
    created(){
      this.getData();
    },
    methods: {
      routerLink(path){
        this.$router.push(path);
      },
      getData(){
        axios.get('https://bird.ioliu.cn/v2?url=https://c.y.qq.com/v8/fcg-bin/fcg_myqq_toplist.fcg?g_tk=5381&uin=0&format=json&inCharset=utf-8&outCharset=utf-8&notice=0&platform=h5&needNewCode=1&_=1533976214289')
          .then((res) =>{
            this.photos = res.data.data.topList;

          })
          .catch((error) =>{
            console.log(error);
          });
      }
    },
  })

</script>


<style scoped>

</style>
