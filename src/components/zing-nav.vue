<template>
  <nav>
    <div class="logo">
      {{logoText}}
    </div>
    <ul :class="'nav-menu'+(active?' active':'')">
      <li v-for="(item,index) in menu"
          :key="'nav-menu-'+index"
          @click="onChange(index)">{{item}}</li>
    </ul>
    <div class="berger"
         @click="active=!active">
      <div class="top-line"></div>
      <div class="midle-line"></div>
      <div class="bottom-line"></div>
    </div>
  </nav>
</template>

<script>

export default {
  data () {
    return {
      active: false
    }
  },
  props: {
    logoText: String,
    menu: Array

  },
  methods: {
    onChange (index) {
      this.$emit('onChange', index)
    }
  }
}
</script>
<style>
:root {
  --primary-color: #7698b3;
  --text-primart-color: #dadbdd;
}
nav {
  display: flex;
  justify-content: space-between;
  box-sizing: border-box;
  font-family: "PingFang SC", "MiscroSoft Yahei", sans-serif;
  padding: 0 5vw;
  align-items: center;
  background-color: var(--primary-color);
  height: 60px;
}
nav .logo {
  font-weight: 600;
  font-size: 24px;
  color: white;
}
nav .nav-menu {
  display: flex;
  justify-content: space-between;
  list-style: none;
  color: var(--text-primart-color);
}
nav .nav-menu li {
  margin-right: 40px;
  cursor: pointer;
}
.berger {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 30px;
  cursor: pointer;
  display: none;
}
.berger div {
  width: 25px;
  height: 3px;
  margin: 4px;
  background-color: var(--text-primart-color);
}
@media screen and (max-width: 768px) {
  .berger {
    display: block;
  }
  .nav-menu {
    position: absolute;
    top: 60px;
    right: 0;
    background: var(--primary-color);
    display: flex;
    flex-direction: column;
    height: calc(100% - 60px);
    justify-content: flex-start !important;
    width: 40vw;
    transition: 0.3s ease-in-out;
    transform: translate(100%);
  }
  .nav-menu.active {
    transform: translate(0);
  }
  .nav-menu li {
    margin: 20px 0;
    text-align: center;
    width: 100%;
  }
}
</style>
