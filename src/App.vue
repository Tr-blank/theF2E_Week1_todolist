<template>
  <body id="app">
    <noscript>
      <strong>We're sorry but thr doesn't work properly without JavaScript enabled. Please enable it to continue.</strong>
    </noscript>
    <header>
      <nav class="navThree-now1">
        <router-link class="navItem now" to="/">My Tasks</router-link>
        <router-link class="navItem" to="/about">In Progress</router-link>
        <router-link class="navItem" to="/about">Completed</router-link>
      </nav>
    </header>
    <main>
      <div class="listItem">
        <div class="listTitle">
          <div>
              <i class="icon fas fa-check-square"></i>
              <span class="title">Type Something Here...</span>
          </div>
          <div>
            <i class="icon far fa-star"></i>
            <i class="icon fas fa-pencil-alt"></i>
          </div>
        </div>
        <ul class="listContent">
          <li class="listContentLine"><i class="far fa-calendar-alt"></i><span class="listContentTitle">Deadline</span>
            <input class="deadline_date" type="date" value="2018/5/14">
            <input class="deadline_time" type="time" value="14:30">
          </li>
          <li class="listContentLine"><i class="far fa-file"></i><span class="listContentTitle">File</span><input type="file"></li>
          <li class="listContentLine"><i class="far fa-comment-dots"></i><span class="listContentTitle">Comment</span><textarea></textarea></li>
          <li>
            <button class="buttonCancel"><i class="fas fa-times"></i>Cancel</button>
            <button class="buttonMain"><i class="fas fa-plus"></i>AddTask</button>
          </li>
        </ul>
      </div>
      <div class="listItem list-Important">
        <div class="listTitle">
          <div>
            <i class="icon fas fa-check-square"></i>
            <span class="title">Type Something Here...</span>
          </div>
          <div>
            <i class="icon far fa-star"></i>
            <i class="icon fas fa-pencil-alt"></i>
          </div>
        </div>
      </div>
      <div class="listItem ">
        <div class="listTitle">
          <div>
            <i class="icon fas fa-check-square"></i>
            <span class="title">Type Something Here...</span>
          </div>
          <div>
            <i class="icon far fa-star"></i>
            <i class="icon fas fa-pencil-alt"></i>
          </div>
        </div>
      </div>
      <div class="listItem list-Complete">
        <div class="listTitle">
          <div>
            <i class="icon fas fa-check-square"></i>
            <span class="title">Type Something Here...</span>
          </div>
          <div>
            <i class="icon far fa-star"></i>
            <i class="icon fas fa-pencil-alt"></i>
          </div>
        </div>
      </div>
      <div class="listItem list-Complete list-Important">
        <div class="listTitle">
          <div>
            <i class="icon fas fa-check-square"></i>
            <span class="title">Type Something Here...</span>
          </div>
          <div>
            <i class="icon far fa-star"></i>
            <i class="icon fas fa-pencil-alt"></i>
          </div>
        </div>
      </div>
      <div class="listTotal">4 tasks left</div>
    </main>
    <!-- <router-view/> -->
    <footer>Copyright © 2018 By 提亞 All rights reserved</footer>
  </body>
</template>

<style lang="stylus">
@import 'stylus/normalize'
@import 'stylus/basic'
@import 'stylus/home'
</style>
