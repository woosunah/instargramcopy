<template>
  <div class="home">
    <div class="home-content">
    <core-app-bar></core-app-bar>
    <core-view />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: "Home",
  components: {
    CoreAppBar:() => import("@/components/core/AppBar.vue"),
    CoreView:() => import("@/components/core/View.vue"),


  }
};
</script>
<style lang="scss" scoped>
.home {
  background:#e7e7e7;
  display:flex;
  flex-flow:row;
  justify-content:center;
}
.home-content{
  background:#fff;
  min-width:560px;
  min-height:100vh;
}
</style>
