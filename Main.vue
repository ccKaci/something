<template lang="html">
  <div>
    <li><a @click="turndown">顶部下拉菜单</a></li>
    <li><a @click="turnleft">右侧拉动菜单</a></li>
    <li><a @click="turnup">下部上拉菜单</a></li>
    <li><a @click="double">双层菜单</a></li>
    <li><a @click="leftlist">左滑菜单</a></li>
  </div>
</template>

<script>
export default {
  methods: {
    turndown() {
      this.$router.push({path:'/turndown'})
    },
    turnup() {
      this.$router.push({path:'/turnup'})
    },
    turnleft() {
      this.$router.push({path:'/turnleft'})
    },
    double() {
      this.$router.push({path:''})
    },
    leftlist() {
      this.$router.push({path:''})
    }
  }
}
</script>

<style lang="css">

</style>
