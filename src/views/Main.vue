<template>
  <div>
    <story-slider></story-slider>
    <post v-for="(post, i) in posts" :key="i" :post="post"></post>
    <post-item></post-item>
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'Main',
  components: {
    StorySlider: () => import('@/components/main/StorySlider.vue'),
    Post: () => import('@/components/main/Post.vue'),
  },
  computed: {
    ...mapState(['posts']),
  },
};
</script>

<style lang="scss" scoped></style>
