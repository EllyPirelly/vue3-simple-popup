<template>
  <div class="home">
    <h1>{{ title }}</h1>
    <p>Click "About" in navigation to get to the modals</p>
  </div>
</template>

<script>
export default {
  name: 'Home',

  data() {
    return {
      title: 'Just another Vue app',
    }
  },
}
</script>

<style lang="scss">
.home {
  margin-top: 30px;
}
</style>
