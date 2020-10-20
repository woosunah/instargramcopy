<template>
  <div class="post-component">
    <v-row class="post-head" align="center" no-gutters>
      <v-avatar size="40" class="head-avatar">
        <v-img :src="post.userProfile.img" alt="post.name"></v-img>
      </v-avatar>
      <h3>{{ post.userProfile.name }}</h3>
      <v-spacer></v-spacer>
      <v-btn x-large icon>
        <v-icon>mdi-dots-horizontal</v-icon>
      </v-btn>
    </v-row>
    <div class="img-container">
      <v-img
        :src="post.content.img"
        max-height="597"
        min-height="479"
        contain
      ></v-img>
    </div>
    <post-item></post-item>
    <like :like="post.like"></like>
  </div>
</template>

<script>
export default {
  name: 'Post',
  props: ['post'],
  components: {
    PostItem: () => import('@/components/main/PostItem.vue'),
    Like: () => import('@/components/main/Like.vue'),
  },
};
</script>

<style lang="scss" scoped>
.post-head {
  text-align: start;
  height: 60px;
  width: 100%;
  // vw 스크린 창 width 100%
  border-bottom: 1px solid #80808054;
  // 808080은 컬러 핵사코드 뒤에 54는 opacity
  .head-avatar {
    margin-left: 20px;
  }
  h3 {
    font-size: 1.7rem;
    font-weight: bold;
    display: inline-block;
    margin: 0 20px;
  }
}
</style>
