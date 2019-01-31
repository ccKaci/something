<template>
  <div class="slider_contain" style="background: #f3f9ff;">
    <div class="slider">
      <div class="list">
        <div class="middleTo middleTo-bottom" style="height: calc(100% - 51px);;overflow:auto;">
          <div style="height: 100%;overflow:auto;">
          <ul class="group">
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 个人情况</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 列表2</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 公司报表</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 资金报表</div>
            </li>
          </ul>
          <l-group>
          <ul slot="inbox" class="group">
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 个人情况</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 列表2</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 公司报表</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 资金报表</div>
            </li>
          </ul>
          </l-group>
          <l-group>
          <ul slot="inbox" class="group">
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 个人情况</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 列表2</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 公司报表</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 资金报表</div>
            </li>
          </ul>
          </l-group>
          <l-group>
          <ul slot="inbox" class="group">
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 个人情况</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 列表2</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 公司报表</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 资金报表</div>
            </li>
          </ul>
          </l-group>
          <l-group>
          <ul slot="inbox" class="group">
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 个人情况</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 列表2</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 公司报表</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 资金报表</div>
            </li>
          </ul>
          </l-group>
          <l-group>
          <ul slot="inbox" class="group">
            <div style="width: 100%;height: 20px; background: #ccc;"></div>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 个人情况</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 列表2</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 公司报表</div>
            </li>
            <li class="waves list-slide">
                <div class="linkTo" @click="goTo()"> 资金报表</div>
            </li>
          </ul>
          </l-group>
        </div>
        </div>
        <div class="bottomTo">
          <div style="padding: 10px 15px;display: flex;color: #fff;line-height: 30px;"><i class="fa fa-user" style="padding: 0px 5px;vertical-align: middle; line-height: 30px;"></i>切换报表</div>
        </div>
      </div>
      <div style="width: calc(100% - 0px); background: rgba(221, 221, 221, 0.58);right: 0;height: inherit; position: absolute;" v-show="black"></div>
    </div>
    <div class="content">
      <div class="btn" @click="launch1 = !launch1"><i class="fa fa-angle-double-right" aria-hidden="true"></i></div>
      <transition name="transition">

        <!-- <keep-alive>
          <router-view></router-view>
        </keep-alive> -->
      </transition>
    </div>
  </div>
</template>

<script>
import LGroup from '../draw/group/LGroup'
  export default {
    name: 'slider',
    components: {
      LGroup
    },
    data () {
      return {
        height:window.innerHeight,
        launch1:false,
    	  fundRes: '',
        black: false
      }
    },
    methods:{
      goTo(){

      }
    },
    watch:{
      launch1(val){
        var mythis = this
        if(val){
          document.querySelector('.list').style.transform= 'translateX(0px)'
          document.querySelector('.list').style.boxShadow= '2px 0 2px #ccc'
          document.querySelector('.content').style.transform='translateX(240px)'
          document.querySelector('.content').style.width = '100%'
          document.querySelector('.btn i').setAttribute('class','fa fa-angle-double-left')
          mythis.black = true
        }else{
          document.querySelector('.list').style.transform= 'translateX(-240px)'
          document.querySelector('.list').style.boxShadow= '0px 0 0px #ccc'
          document.querySelector('.content').style.transform='translateX(0px)'
          document.querySelector('.content').style.width = '100%'
          document.querySelector('.btn i').setAttribute('class','fa fa-angle-double-right')
          mythis.black = false
        }
      }
    }
  }
</script>

<style scoped>
  .content{
    transition: transform ease-in-out 0.38s, visibility 0.38s, -webkit-transform ease-in-out 0.38s;
    transform: translateX(0px);
    height: 100%;
    width: 100%;
    position: absolute;
    top:0;
    z-index:3;
  }
.slideList {
position: absolute;
width: 16px;
height: inherit;
top: 0;
right: 0;
-webkit-user-select:none;
-moz-user-select:none;
-ms-user-select:none;
user-select:none;
}
.weui-cell{
font-size: 0.82rem !important;
color: #282828 !important;
padding: 10px !important;
}
.vux-label{
cursor:pointer;
}
.weui-cell:before {
left: 5px !important;
right: 10px !important;
}
.weui-cell:after {
right: 10px !important;
}
.list-title{
margin-top: 0 !important;
margin-bottom: 0 !important;
padding-left: 15px;
padding-right: 15px;
color: #999999;
font-weight: bold;
display:block;
font-size:15px !important;
background:#71a9d2;
color:#fff;
}
.weui-cells__title {
  margin-top: 0 !important;
  margin-bottom: 0 !important;
  padding-left: 15px;
  padding-right: 15px;
  font-size: 0.7rem !important;
  font-weight: bold !important;
  background:#f5f5f5;
}
  .list{
    background: #fff;
    /* overflow: auto; */
    /* border-right: 1px solid #ddd; */
    width:240px;
    transform: translateX(-240px);
    -webkit-tap-highlight-color:rgba(0,0,0,0);
    position: absolute;
    -webkit-overflow-scrolling : touch;
    z-index: 5;
    height: inherit;
    transition: transform ease-in-out 0.38s, visibility 0.38s, -webkit-transform ease-in-out 0.38s;
  }
  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  li {
    display: inline-block;
    margin: 0;
  }
  .slider_contain{
    height: 100%;
    width: 100%;
  position: relative;
  overflow: hidden;
  }

  .slider{
    left:0px;
    height:100%;
    display: flex;
    z-index: 1;
  }
  li.list-slide{
    margin: 0;
    padding: 5px 8px;
    -webkit-box-align: center;
    align-items: center;
    font-size: .9rem;
    cursor: pointer;
    width: -webkit-fill-available;
    position: relative;
}
  /* li.list-slide:before {
    content: " ";
    position: absolute;
    left: 0;
    top: -1px;
    right: 10px;
    height: 1px;
    border-top: 1px solid #D9D9D9;
    color: #D9D9D9;
    transform-origin: 0 0;
    transform: scaleY(0.5);
  }
  li.list-slide:after {
      content: " ";
    position: absolute;
    left: 0;
    bottom: 0;
    right: 10px;
    height: 1px;
    border-bottom: 1px solid #D9D9D9;
    color: #D9D9D9;
    -webkit-transform-origin: 0 100%;
    transform-origin: 0 100%;
    -webkit-transform: scaleY(0.5);
    transform: scaleY(0.5);
  } */

    .btn{
      position: absolute;
      top: 50px;
      left: 0px;
      z-index: 999;
      transition: transform ease-in-out 0.38s, visibility 0.38s, -webkit-transform ease-in-out 0.38s;
      font-size: 28px;
      border: 1px solid #ccc;
      padding: 0 10px;
      background: #fff;
      /* background: rgba(221, 221, 221, 0.28); */
      color: #71a9d2;
      border-bottom-right-radius: 8px;
      border-top-right-radius: 8px;
      box-shadow: 0 3px 5px #e4e4e4, 0 -3px 5px #e4e4e4;
      display: block;
    }
    .bottomTo{
      /* position: sticky; */
    /* bottom: 0; */
    /* left: 0; */
    /* width: 100%; */
    height: 50px;
    /* display: block; */
    background: #67b0fb;
    box-shadow: 0 -2px 2px #ccc;

    width: 240px;
    /* height: 41px; */
    /* background: url('../assets/bottomTo2.jpg'); */
    left:0px;
    bottom:0px;
    border-top: 1px solid #cdcdcd;
    box-shadow: 0px -2px 1px #cdcdcd;
    position: absolute;
    }
</style>
