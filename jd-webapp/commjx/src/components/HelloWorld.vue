<template>
  <div>
      <van-nav-bar
              left-text="返回"
              title="购物车"
              left-arrow
              @click-left="onClickLeft"
      />

    <van-card
            num="2"
            :key="i"
            v-for="(p,i) in list"
            :price="p.fontprize"
            :desc="p.fonteqiu"
            :title="p.fontphoto"
            thumb="https://openfile.meizu.com/group1/M00/06/CC/Cgbj0VvINL-AGM20AAw4GirVtYA698.png@240x240.jpg"
    >
      <div slot="tags">
        <van-tag plain type="danger">加价购</van-tag>
        <van-tag plain type="danger">特价购</van-tag>
      </div>
      <div slot="footer">
        <van-button size="mini">删除</van-button>
        <van-button size="mini">添加</van-button>
      </div>
    </van-card>
    <van-tabbar v-model="active">
          <van-tabbar-item icon="home-o" @click-left="onClickLeft">首页</van-tabbar-item>
          <van-tabbar-item icon="search">详情</van-tabbar-item>
          <van-tabbar-item icon="friends-o">购物车</van-tabbar-item>
          <van-tabbar-item icon="setting-o">我的</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
    import { NavBar } from 'vant';
  import { Card,Tag,Tabbar,TabbarItem } from 'vant';
  import { button } from "vant"
export default {
  name: 'HelloWorld',
  components:{
      "van-card":Card,
      "van-nav-bar":NavBar,
      "van-tag":Tag,
      "van-button":button,
      "van-tabbar":Tabbar,
      "van-tabbar-item":TabbarItem
  },
    data(){
      return {
          active:0,
          list:[
              {
                  fonteqiu: "魅族 Note9",
                  fontprize:"1199.00",
                  fontphoto:"4800万|前置2000万|独家定制水滴设计全面屏|4000Ah大"
              },{
                  fonteqiu: "魅族 16s Pro",
                  fontprize:"2199.00",
                  fontphoto:"【限时3期免息】骁龙845 | 屏幕下指纹 | 前后2000万像素摄像头"
              }
              ],

      }
    },
  props: {
    msg: String
  },
    methods:{
        onClickLeft() {
            this.$router.replace('/list')
        },
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
