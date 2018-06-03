<template>
<div>
  <section class="navone-left">

    <li>

      <img src="//cdn.cnbj0.fds.api.mi-img.com/b2c-mimall-media/53d32c5e55cba00b473b48908c571f02.jpg?thumb=1&w=360&h=360" alt="">
      <div>
        <p style="font-size: 0.28rem;color: rgba(0,0,0,.87);">小米MIX 2S</p>
        <p style="margin-top: .06rem; font-size: .22rem;line-height: .3rem;color: rgba(0,0,0,.54);white-space: nowrap;
                     overflow: hidden;
                        text-overflow: ellipsis;">骁龙845旗舰处理器，AI双摄</p>
        <p style="font-size: .28rem; color: #ea625b; height: 1.5em; line-height: 1.5em; position: relative;  display: inline-block;">¥3299起</p>
      </div>

    </li>

    <li>
      <img src="//cdn.cnbj0.fds.api.mi-img.com/b2c-mimall-media/ee44583e8167f3d250186069a26c1384.jpg?thumb=1&w=360&h=360">
      <div>
        <p style="font-size: 0.28rem;color: rgba(0,0,0,.87);">小米MIX 2S</p>
        <p style="margin-top: .06rem; font-size: .22rem;line-height: .3rem;color: rgba(0,0,0,.54);white-space: nowrap;
                     overflow: hidden;
                        text-overflow: ellipsis;">骁龙845旗舰处理器，AI双摄</p>
        <p style="font-size: .28rem; color: #ea625b; height: 1.5em; line-height: 1.5em; position: relative;  display: inline-block;">¥3299起</p>
      </div>
    </li>
  </section>
  <section class="navone-left">
    <li v-for="i in zhi">
      <img :src="i.pic" alt="">
      <div>
      <p style="font-size: 0.28rem;color: rgba(0,0,0,.87);"> {{i.author}}</p>
      <p style="margin-top: .06rem; font-size: .22rem;line-height: .3rem;color: rgba(0,0,0,.54);white-space: nowrap;
                     overflow: hidden;
                        text-overflow: ellipsis;">{{i.title}}</p>
      <p style="font-size: .28rem; color: #ea625b; height: 1.5em; line-height: 1.5em; position: relative;  display: inline-block;">¥3299起</p>
      </div>
    </li>
  </section>
</div>
</template>

<script>
  import axios from  'axios'
    export default {
    data(){
      return {
        zhi:['']
      }

    },
      mounted(){
        axios.get('/shuju').then((res)=>{
          // console.log(res);
          this.zhi=res.data.articles
          // console.log(this.zhi)
        });
        // axios.get('/xiangqin').then((res)=>{
        //   console.log(res);
        // })
      },
    }
</script>

<style scoped lang="scss">
  .navone-left{
    padding: 0.2rem;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    li{
      margin-right: .04rem;
      width: 48%;
      img{
        width: 100%;
      }
      div{
        padding: .2rem .27rem;
        text-align: left;
      }
    }
  }
</style>
