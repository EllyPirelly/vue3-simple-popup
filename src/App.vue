<template>
  <div id="nav">
    <router-link to="/">Home</router-link>
    <span> | </span>
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
</template>

<script>
//
</script>

<style lang="scss">
#app {
  font-family: 'Bitter', serif;
  text-align: center;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
}

#nav {
  padding-top: 30px;

  a {
    color: #2c3e50;
    font-weight: bold;

    &.router-link-exact-active {
      color: #d2691e;
    }

    &:hover {
      color: #efb082;
    }
  }
}
</style>
