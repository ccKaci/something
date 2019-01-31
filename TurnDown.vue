<template>
  <div class="slider_contain" style="background: #f3f9ff;">
    <div class="slider">
      <div class="down">
        <div style="width:inherit;height:inherit;padding: 0 5px;">
          <div style="width:30%;height: 110px;display: inline-block;float:left;margin: 5px;" v-for="e in 9">
            <div style="width:100%;height: inherit; background: #ccc;border: 1px solid #fff;"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="content">
      <div class="btn" @click="launch1 = !launch1"><i class="fa fa-angle-double-down" aria-hidden="true"></i></div>
      <transition name="transition">

        <!-- <keep-alive>
          <router-view></router-view>
        </keep-alive> -->
      </transition>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'slider',
    data () {
      return {
        height:window.innerHeight,
        launch1:false,
    	  fundRes: '',
      }
    },
    methods:{
      goTo(){

      }
    },
    watch:{
      launch1(val){
        if(val){
         // console.log('展开')
          document.querySelector('.down').style.transform= 'translateY(0px)'
          document.querySelector('.content').style.transform='translateY(380px)'
          document.querySelector('.content').style.width = '100%'
          document.querySelector('.btn i').setAttribute('class','fa fa-angle-double-up')
        }else{
         // console.log('收起')
          document.querySelector('.down').style.transform= 'translateY(-380px)'
          document.querySelector('.content').style.transform='translateY(0px)'
          document.querySelector('.content').style.width = '100%'
          document.querySelector('.btn i').setAttribute('class','fa fa-angle-double-down')
        }
      }
    }
  }
</script>

<style scoped>
  .content{
    transition: transform ease-in-out 0.38s, visibility 0.38s, -webkit-transform ease-in-out 0.38s;
    transform: translateY(0px);
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
/* // 遮罩 设置背景层，z-index值要足够大确保能覆盖，高度 宽度设置满 做到全屏遮罩 */
.slideList-in {
top: 15px;
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
  .down{
    background: #fff;
    overflow: auto;
    border-right: 1px solid #ddd;
    width:100%;
    height: 370px;
    border-bottom: 10px solid #fff;;
    transform: translateY(-380px);
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
  }

  li {
    display: inline-block;
    margin: 0;
  }
  .slider_contain{
    /* height: 700px; */
    /* width: 320px; */
    width: inherit;
    height: inherit;
  position: relative;
  overflow: hidden;
  }

  .slider{
    top:0px;
    width:100%;
    height: 370px;
    display: flex;
    z-index: 1;
  }
  li.list-slide{
    margin: 0;
    padding: 10px 8px;
    -webkit-box-align: center;
    align-items: center;
    font-size: 0.9rem;
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
  } */
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
  }

    .btn{
      position: absolute;
      top: 0px;
      left: 50px;
      z-index: 999;
      transition: transform ease-in-out 0.38s, visibility 0.38s, -webkit-transform ease-in-out 0.38s;
      font-size: 28px;
      border-top: 0px solid #ccc;
      border: 1px solid #ccc;
      padding: 0 10px;
      background: rgba(221, 221, 221, 0.28);
      color: #71a9d2;
      border-bottom-left-radius: 8px;
      border-bottom-right-radius: 8px;
      box-shadow: 0 3px 5px #dadada, 0 -3px 5px #dedede;
      display: block;
    }
</style>
