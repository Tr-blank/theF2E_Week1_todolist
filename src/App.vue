<template>
  <body id="app">
    <noscript>
      <strong>We're sorry but thr doesn't work properly without JavaScript enabled. Please enable it to continue.</strong>
    </noscript>
    <!-- <label for="navControl"><i class="fas fa-bars"></i></label>
    <input class="hide" type="checkbox" id="navControl">
    <header>
      <label for="navControl"><i class="fas fa-times"></i></label>
      <h1>第一周 待辦清單｜提亞</h1>
      <h2>The F2E - 前端修練精神時光屋 前端工程組</h2>
      <nav class="navMain">
         <router-link class="navItem " to="/">個人設計</router-link> 
        <router-link class="navItem now" to="/original">官方設計</router-link>
      </nav>
    </header> -->
    <router-view/>

  </body>
</template>

<style lang="stylus">
@import 'stylus/normalize'

header
  position: fixed;
  width: 320px;
  height: 100%;
  background-color:#f2f2f2
  z-index: 100;
  right: -320px;
  padding: 10px;
  box-shadow: 0px 0px 5px 0px rgba(0,0,0,.3);
  transition: right .25s ease
  .fa-times
    font-size 1.6rem
    padding 15px
    position absolute
    top 0
    right  0
    z-index  110
.fa-bars
    font-size 1.6rem
    padding 15px
    position fixed
    top 0
    right  0
    z-index  10
#navControl:checked
  + header
    right 0
h1
  font-size 1.3rem
  line-height 2rem
h2
  font-size .9rem
  line-height 2rem
</style>
