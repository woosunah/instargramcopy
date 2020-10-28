<template>
  <div>
    <v-card>
      <v-row class="card-title" justify="center" align="center">
        <v-btn icon @click="dialog.on = false"
          ><v-icon>mdi-close</v-icon></v-btn
        >
        <v-spacer></v-spacer>
        <h3>댓글</h3>
        <v-spacer></v-spacer>
        <v-btn icon><v-icon>mdi-send</v-icon></v-btn>
      </v-row>
      <v-row no gutters align="center" class="comment-text-filed-wrapper">
        <v-avatar><v-img :src="userImg"></v-img></v-avatar>
        <v-text-field
          solo
          flat
          rounded
          placeholder="댓글 달기..."
          class="add-comment-text-filed"
          v-model="myComment"
        >
          <template v-slot:append>
            <v-btn text large color="blue" @click="pushComment">게시</v-btn>
          </template>
        </v-text-field>
      </v-row>
      <div class="comment-user-list">
        <v-row
          v-for="(comment, i) in comments"
          :key="i"
          class="list-item"
          no-gutters
          align="start"
        >
          <!-- no-gutter -> margin:0, padding:0; -->
          <p>
            <strong>{{ comment.name }}</strong> {{ comment.text }}
          </p>
          <v-spacer></v-spacer>
          <v-btn icon x-small><v-icon>mdi-heart-outline</v-icon></v-btn>
        </v-row>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'CommentPush',
  props: ['comments', 'userImg', 'index', 'dialig'],
  data() {
    return {
      myComment: '',
    };
  },
  methods: {
    pushComment() {
      this.$store.commit('pushComment', {
        idex: this.index,
        name: 'me',
        text: this.myComment,
      });
    },
  },
  // methods - mutation은 짝궁 개념 / 함수니까 methods에 실행
};
</script>

<style lang="scss" scoped>
.card-title {
  height: 60px;
  padding: 0 20px;
  border: 1px solid #80808054;

  h3 {
    display: inline-block;
  }
}
.comment-text-filed-wrapper {
  padding: 10px 15px;
  background-color: #eee;
}
.add-comment-text-filed {
  height: 50px;
  margin-left: 10px;
}

.list-item {
  padding: 16px;
  p {
    margin: 0;
    max-width: 90%;
  }
}
</style>
