<!-- 专题首页 -->
<template>
  <div>
    <x-header v-on:click="switch">{{title}}<a slot="right"></a></x-header>
  <div style="margin: 10px;overflow: hidden;" v-for="item in list">
    <masker style="border-radius: 2px;" :opacity="0.5">
      <div class="m-img" :style="{backgroundImage: 'url(' + item.img + ')'}"></div>
      <div slot="content" class="m-title">
        {{item.title}}
        <br/>
        <span class="m-time">{{item.date}}</span>
      </div>
    </masker>
  </div>
</div>
</template>

<script>
  import masker from 'vux-components/masker'
  import xHeader from 'vux-components/x-header'
  import footBottom from '../_block/footBottom'
  export default {
    components: {
      xHeader,
      masker,
      footBottom
    },
    data: function () {
      return {
        title: '专题',
        list: [{
          title: '洗颜新潮流！人气洁面皂排行榜',
          img: 'https://cdn.xiaotaojiang.com/uploads/82/1572ec37969ee263735262dc017975/_.jpg',
          date: '2016-03-18'
        }, {
          title: '美容用品 & 日用品（上）',
          img: 'https://cdn.xiaotaojiang.com/uploads/59/b22e0e62363a4a652f28630b3233b9/_.jpg'
        }, {
          title: '远离车内毒气，日本车载空气净化器精选',
          img: 'https://cdn.xiaotaojiang.com/uploads/56/4b3601364b86fdfd234ef11d8712ad/_.jpg'
        }]
      }
    }
}
</script>

<style>
  .m-img {
  padding-bottom: 33%;
  display: block;
  position: relative;
  max-width: 100%;
  background-size: cover;
  background-position: center center;
  cursor: pointer;
  border-radius: 2px;
}
.m-time {
  font-size: 12px;
  padding-top: 4px;
  border-top: 1px solid #f0f0f0;
  display: inline-block;
  margin-top: 5px;
}
.m-title {
  color: #fff;
  text-align: center;
  text-shadow: 0 0 2px rgba(0,0,0,.5);
  font-weight: 500;
  font-size: 16px;
  position: absolute;
  left: 0;
  right: 0;
  width: 100%;
  text-align: center;
  top: 50%;
  transform: translateY(-50%);
}
</style>
