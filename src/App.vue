<template>
  <div id="app">
    <div id="nav">
      <router-link to="/" v-show="false">Home</router-link>
      <router-link to="/people" v-if="false">Data</router-link>
      <router-link to="/picinfo" v-if="false">PicInfo</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}

#nav {
  padding: 0px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
