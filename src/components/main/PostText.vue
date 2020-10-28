<template>
  <div class="text-container">
    <p>
      <strong>{{ userName }}</strong
      >{{ isMore ? text : text.slice(0, 10) + '...' }}
      <!-- false일때, 실행 - slice(0,10) 0부터 10글자 까지만 보여주는거 -->
      <span @click="isMore = true" v-show="!isMore">더보기</span>
      <!-- 변환 될 예정은 v-show v-if(안보여주려면 아예 안보여주는거) -->
    </p>
  </div>
</template>

<script>
export default {
  name: 'PostText',
  props: ['userName', 'text'],
  // :userName="post.userProfile.name" post.vue파일에서 지정해줌
  data() {
    return {
      isMore: false,
    };
    // isMore에 false가 기본 설정으로 되어있으니까 첫화면에서 안보임,
  },
};
</script>

<style lang="scss" scoped>
.text-container {
  padding: 0 16px;
}
</style>
