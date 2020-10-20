<template>
  <v-footer absolute>
    <v-row justify="center" align="center" dense>
      <v-col cols="2" v-for="(tab, i) in tabs" :key="i">
        <router-link :to="tab.to"
          ><v-btn icon
            ><v-icon>{{ tab.icon }}</v-icon></v-btn
          ></router-link
        >
      </v-col>
      <v-col cols="2">
        <router-link to="/"
          ><v-btn icon
            ><v-avatar size="30"
              ><v-img
                src="https://6.vikiplatform.com/image/a11230e2d98d4a73825a4c10c8c6feb0.jpg?x=b&a=0x0&s=590x330&q=h&e=t&f=t&cb=1"
              ></v-img></v-avatar></v-btn
        ></router-link>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  name: 'CoreFooter',
  data() {
    return {
      tabs: [
        { to: '/', icon: 'mdi-home-variant' },
        { to: '/', icon: 'mdi-magnify' },
        { to: '/', icon: 'mdi-plus-box' },
        { to: '/', icon: 'mdi-heart-outline' },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
