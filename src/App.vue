<template>
  <div id="app">
    <zingNav logoText="邓志鑫"
             :menu="menu"
             @onChange="onChange"></zingNav>
  </div>
</template>

<script>
import zingNav from './components/zing-nav.vue'
export default {
  name: 'App',
  components: {
    zingNav
  },
  data () {
    return {
      menu: ['首页', '我的作品', '我的简历', '关于']
    }
  },
  methods: {
    onChange (index) {
      alert(index)
    }
  }
}
</script>

<style>
html,
body,
#app {
  width: 100%;
}
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
