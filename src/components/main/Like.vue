<template>
  <div class="like-container">
    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on, attrs }">
        <p>
          <strong>{{ like[0] }}</strong> 님
          <span style="font-weight:bold;" v-bind="attrs" v-on="on">여러 명</span
          >이 좋아합니다
        </p>
      </template>

      <v-card>
        <v-row class="card-title" justify="center" align="center">
          <v-btn icon @click="dialog = false"><v-icon>mdi-close</v-icon></v-btn>
          <v-spacer></v-spacer>
          <h3>좋아요</h3>
          <v-spacer></v-spacer>
          <v-btn icon style="opacity:0;" disabled
            ><v-icon>mdi-close</v-icon></v-btn
          >
        </v-row>
        <div class="like-user-list">
          <v-row
            v-for="(user, i) in like"
            :key="i"
            class="list-item"
            no-gutters
            align="center"
          >
            <!-- no-gutter -> margin:0, padding:0; -->
            <p>{{ user }}</p>
            <v-spacer></v-spacer>
            <v-btn color="blue" dark>팔로우</v-btn>
          </v-row>
        </div>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: 'Like',
  props: ['like'],
  data() {
    return {
      dialog: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.like-container {
  padding: 0 16px;
}
.card-title {
  height: 60px;
  padding: 0 20px;
  border: 1px solid #80808054;

  h3 {
    display: inline-block;
  }
}
.list-item {
  height: 70px;
  padding: 10px 20px;
  width: 100%;
  // 하단 스크롤바 생김 방지 width:100%

  p {
    display: inline-block;
    font-size: 1.9rem;
    font-weight: bold;
    margin: 0;
  }
}
</style>
