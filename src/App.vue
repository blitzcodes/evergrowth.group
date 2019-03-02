<template>
  <div id="app">
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
  export default {
    name: 'app',
  }
</script>

<style lang="scss">
  $c-brand-green: rgb(101, 138, 160);

  body {
    margin: 0;
    background: $c-brand-green;
    overflow-x: hidden;
  }

  #app {
    font-family: 'Roboto', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #fff;
  }
</style>
