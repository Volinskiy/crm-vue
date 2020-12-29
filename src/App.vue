<template>
  <div id="app">

    <component :is="layout">
      <router-view/>

    </component>
  </div>
</template>

<script>
import AuthLayout from '@/layouts/AuthLayout.vue';
import MainLayout from '@/layouts/MainLayout.vue';

export default {
  computed: {
    layout() {
      console.log(this.$route.meta);
      return `${this.$route.meta.layout || 'main'}-layout`;
    },
  },
  components: {
    AuthLayout,
    MainLayout,
  },
};
</script>

<style lang="less">
@import '~materialize-css/dist/css/materialize.min.css';
@import 'assets/index.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
