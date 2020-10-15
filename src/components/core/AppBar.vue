<template>
  <v-app-bar color="white">
    <img class="logo" src="../../assets/img/logo.png" alt="logo">
    <v-text-field class="search"
            placeholder="검색"
            prepend-inner-icon="mdi-magnify"
            filled
            dense
            style="top:14px"
          >
          </v-text-field>
          <v-btn icon><v-icon>mdi-home</v-icon></v-btn>
          <v-btn icon><v-icon>mdi-send-outline</v-icon></v-btn>
          <v-btn icon><v-icon>mdi-compass-outline</v-icon></v-btn>
          <v-btn icon><v-icon>mdi-heart-outline</v-icon></v-btn>
          <v-avatar size="30">
            <v-img src="https://6.vikiplatform.com/image/a11230e2d98d4a73825a4c10c8c6feb0.jpg?x=b&a=0x0&s=590x330&q=h&e=t&f=t&cb=1"></v-img>
          </v-avatar>
  </v-app-bar>
</template>

<script>
  export default {
    name:"AppBar",
    data() {
      return {
      }
    },
  }
</script>

<style lang="scss" scoped>
.logo {
  height:30px;
  margin-left:10px;
}

.search{
  margin:0 20px 0 20px;
}
</style>