<template>
  <div class="bodys">
    <div>
      <ul class="box-ul">
        <li v-for="(item,index) in photos" :key="index" class="list" @click="routerLink('music')">
          <div class="box-div">
            <img :src="item.picUrl" alt="">
            <div class="box-content">
              <h4>{{ item.topTitle }}</h4>
              <p>{{ item.songList[0].songname }}--{{ item.songList[0].singername }}</p>
            </div>
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
.bodys{
  background: rgba(0,0,0,0.2);
}
.box-ul{
padding: 10px 10px 10px 10px;
overflow: hidden;
}
.box-ul li{
  height: 100px;
  margin-bottom: 10px;
  background: white;
}
.box-div{
    height: 100px;
  display: flex;
  }
.box-div img{
  height: 100px;
  flex:1;
}
  .box-content{
    flex:2;
    height: 100px;
    padding: 5px 0 5px 5px;
  }
  .box-content p{
    font-size: 14px;
  }
</style>
