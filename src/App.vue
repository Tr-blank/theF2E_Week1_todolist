<template>
  <body id="app">
    <noscript>
      <strong>We're sorry but thr doesn't work properly without JavaScript enabled. Please enable it to continue.</strong>
    </noscript>
    <div id="nav">
      <router-link to="/">My Tasks</router-link> |
      <router-link to="/about">In Progress</router-link>
      <router-link to="/about">Completed</router-link>
    </div>
    <router-view/>
  </body>
</template>

<style lang="stylus">
#app
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50

#nav
  padding 30px
  a
    font-weight bold
    color #2c3e50
    &.router-link-exact-active
      color #42b983
</style>
