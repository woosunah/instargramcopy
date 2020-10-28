<template>
  <v-app>
    <router-view></router-view>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
a {
  text-decoration: none;
}

// careful : css about vuetify components
.plus-badge > span > span {
  left: calc(100% - 30px) !important;
  // 이미지 너비 가로길이의 100%에서 30px뺀 값에 위치
  top: calc(100% - 30px) !important;
}
</style>
