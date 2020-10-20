<template>
  <div class="story-slider">
    <div class="wrapper">
      <div class="story-item">
        <v-badge
          bordered
          color="blue"
          icon="mdi-plus"
          overlap
          bottom
          class="plus-badge"
        >
          <!-- offset-x="30"
        offset-y="30" 위에 offset삭제하고 대신 App.vue에서 css로 넣는방법도 있어서 주석처리함 -->
          <!-- 내스토리 사진에 블루아이콘에 + 표시 -->
          <img :src="myProfile.img" alt="myProfile.name" />
        </v-badge>
        <p>내 스토리</p>
      </div>
      <div class="story-item" v-for="(story, i) in stories" :key="i">
        <img :src="story.img" alt="story.name" />
        <p>{{ story.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  computed: {
    ...mapState(['stories', 'myProfile']),
  },
};
</script>

<style lang="scss" scoped>
.story-slider {
  overflow-x: auto;
  // x축으로 내용 넘칠때, scroll되게 하는것
  background: #fafafa;
  border-bottom: 1px solid #80808054;
}

div::-webkit-scrollbar {
  display: none !important;
}

.wrapper {
  width: 1000px;
  white-space: nowrap;
  padding: 10px;
}

.story-item {
  width: 100px;
  height: 100px;
  display: inline-block;
  margin-right: 10px;

  img {
    vertical-align: middle;
    margin: 10px;
    width: 80px;
    height: 80px;
    border-radius: 40px;
    object-fit: cover;
  }

  p {
    text-align: center;
  }
}
</style>
