<template lang="pug">
  #app
    #nav
      router-link(to="/").title Welcome to Infinite-Scroll
      //- span  |
      //- router-link(to="/about") About
    router-view
    footer.footer
      .content.has-text-centered
        p 
          strong Infinite-Scroll 
          | by 
          a(href="https://github.com/mutsuki333") Evan Chen
</template>

<script>
import "babel-polyfill"
import "src/theme.sass"

</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
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
