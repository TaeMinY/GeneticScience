
<template>
  <v-app>
    <v-content>
      <div id="screen">
        <div>기본설정</div>
      </div>
    </v-content>
  </v-app>
</template>
<script>
export default {
  name: "App",
  components: {},
  data() {
    return {};
  },
  methods: {}
};
</script>
<style scoped>
#app {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
#screen {
  width: 80%;
  height: 70%;
}
.nav {
  z-index: 30;
}
</style>