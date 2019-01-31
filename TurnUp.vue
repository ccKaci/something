<template>
  <div class="slider_contain" style="background: #f3f9ff;">
  从底部向上滑
    <div class="slider">
      <div class="down">
        <div style="width:inherit;height:inherit;background: #fff">
          <div  @click="launch1 = !launch1" style="height: 20px;width: 100%; text-align: center;font-size: 1.0rem">
            <span><i class="fa fa-angle-down" aria-hidden="true"></i></span>
          </div>
          <div style="height: 90px;width: 100%; border-bottom: 1px solid #ccc;overflow: hidden;">
            <ul class="list1" style="height: 300px;box-sizing: border-box;overflow-x: scroll; overflow-y: hidden; padding: 0 0 0 8px; white-space: nowrap;width: 100%;">
              <li v-for="i in 9" style="margin: 0 10px;">
                <div style="width:50px; height: 50px; background: #ccc; border-radius: 8px;margin: 5px; display: inline-block;"></div>
              </li>
            </ul>
          </div>
          <div style="height: 80px; width: 100%; border-bottom: 1px solid #ccc;"></div>
          <div style="height: 90px; width: 100%; border-bottom: 1px solid #ccc;"></div>
        </div>
      </div>
    </div>
    <div class="content"
    @touchstart.prevent="touchStart"
    @touchmove.prevent="touchMove"
    @touchend="touchEnd" >
      <!-- <div class="btn" @click="launch1 = !launch1"><i class="fa fa-angle-double-down" aria-hidden="true"></i></div> -->
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
        start: ''
      }
    },
    activated() {
    },
    methods: {
      touchStart(e) {
        const touch = e.touches[0]
        this.start = touch.pageY
      },
      touchMove(e) {
        const touch = e.touches[0]
        const deltaY = touch.pageY - this.start
        if(this.start > (this.height-10) && deltaY < 0){
          if(Math.abs(deltaY) > 100){
            document.querySelector('.down').style.transform= 'translateY(calc(100% - 280px))'
            document.querySelector('.down').style.boxShadow= '0 -2px 3px #ccc'
            document.querySelector('.content').style.width = '100%'
          }
        }else{
          if(Math.abs(deltaY) > 100){
            document.querySelector('.down').style.boxShadow= '0 0 0 #ccc'
            document.querySelector('.down').style.transform= 'translateY(calc(100% + 280px))'
            document.querySelector('.content').style.width = '100%'
          }
        }
      },
      touchEnd() {

      },
      goTo() {

      }
    },
    watch:{
      launch1(val){
        var mythis = this
        if(val){
          document.querySelector('.down').style.transform= 'translateY(calc(100% - 280px))'
          document.querySelector('.down').style.boxShadow= '0 -2px 3px #ccc'
          // document.querySelector('.content').style.transform='translateY(380px)'
          document.querySelector('.content').style.width = '100%'
          // document.querySelector('.btn i').setAttribute('class','fa fa-angle-double-up')
        }else{
          document.querySelector('.down').style.boxShadow= '0 0 0 #ccc'
          document.querySelector('.down').style.transform= 'translateY(calc(100% + 280px))'
          // document.querySelector('.content').style.transform='translateY(0px)'
          document.querySelector('.content').style.width = '100%'
          // document.querySelector('.btn i').setAttribute('class','fa fa-angle-double-down')
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
  .down{
    background: #fff;
    overflow: auto;
    border-right: 1px solid #ddd;
    width:100%;
    height: 280px;
    bottom: 0px;
    /* border-bottom: 10px solid #fff; */
    transform: translateY(calc(100% + 280px));
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
    bottom:0px;
    width:100%;
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
      /* top: 0px; */
      bottom: 0px;
      left: 50px;
      z-index: 999;
      transition: transform ease-in-out 0.38s, visibility 0.38s, -webkit-transform ease-in-out 0.38s;
      font-size: 28px;
      border-top: 0px solid #ccc;
      border: 1px solid #ccc;
      padding: 0 10px;
      background: rgba(221, 221, 221, 0.28);
      color: #71a9d2;
      border-top-left-radius: 8px;
      border-top-right-radius: 8px;
      box-shadow: 0 3px 5px #dadada, 0 -3px 5px #dedede;
      display: block;
    }

      .list1::-webkit-scrollbar {/*滚动条整体样式*/
        width: 10px;     /*高宽分别对应横竖滚动条的尺寸*/
        height: 0px;
    }
  .list1::-webkit-scrollbar-thumb {/*滚动条里面小方块*/
        border-radius: 10px;
         -webkit-box-shadow: inset 0 0 0px rgba(0,0,0,0.2);
        background: #535353;
    }
  .list1::-webkit-scrollbar-track {/*滚动条里面轨道*/
        -webkit-box-shadow: inset 0 0 0px rgba(0,0,0,0.2);
        border-radius: 10px;
        background: #EDEDED;
    }
</style>
