<template>
  <div class="box">
    <div class="top" :class="off?(isUp?'sildeUp':'sildeDown'):''">顶部内容可以是导航，搜索</div>
    <div class="content">
       <p>想展现当任何列表如：新闻</p>
       <p>商品列表</p>
       <p>时事话题等等</p> 
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      // 保存每次最新的地址和最后计算的地址
      new_scroll_position:0,
      last_scroll_position:0,
      isUp:false,
      off:false
    }
  },
  components: {
  },
  methods: {
    scroll(){
      // pageYOffset 属性是 scrollY 属性的别名
      // console.log(window.pageYOffset);
      this.last_scroll_position = window.pageYOffset;
      // 正在下滑
      if(this.new_scroll_position< this.last_scroll_position&&this.last_scroll_position>100){
        console.log(`正在下滑${this.new_scroll_position}`);
        this.off= true;
        this.isUp= false;
      }else if(this.new_scroll_position > this.last_scroll_position){
        // 正在上滑
        console.log('正在上滑');
        this.isUp= true;
      }

      this.new_scroll_position = this.last_scroll_position;
    }
  },
  mounted(){
    window.addEventListener('scroll',this.scroll,true)
},
}
</script>

<style lang="less">
@import './assets/css/basic.less';
* {margin: 0; padding: 0;}
.box{
  .top{
    position: fixed;
    line-height: 80/@px2rem;
    background: #fff;
    font-size: 32/@px2rem;
    text-align: center;
    top: 0;
    width: 100%;
  }
  .content{
    height: 3000/@px2rem;
    background: #ccc;
    margin-top: 84/@px2rem;
    font-size: 28/@px2rem;
  }
  .sildeDown{
    transform: translateY(-80/@px2rem);
    transition: .5s ease-out;
  }
  .sildeUp{
    transform: translateY(0);
    transition: .5s ease-out;
  }
}
</style>
