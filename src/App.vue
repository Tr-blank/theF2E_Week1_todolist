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
            <span></span>
            <input type="text" placeholder="Type Something Here...">
          </div>
          <div>
            <i>重要</i>
            <i>修改</i>
          </div>
        </div>
        <div class="listContent">
          <div class="list"><i></i>Deadline</div>
          <div class="list"><date></date><date></date></div>
          <div class="list"><i></i>File</div>
          <div class="list">+</div>
          <div class="list"><i></i>Comment</div>
          <div class="list"><textarea></textarea></div>
          <div><button><i></i>Cancel</button><button><i></i>AddTask</button></div>
        </div>
      </div>
      <div class="listItem">
        <div class="listTitle">
          <div>
            <span></span>
            <input type="text" placeholder="Type Something Here...">
          </div>
          <div>
            <i>重要</i>
            <i>修改</i>
          </div>
        </div>
        <div class="listContent">
          <div class="list"><i></i>Deadline</div>
          <div class="list"><date></date><date></date></div>
          <div class="list"><i></i>File</div>
          <div class="list">+</div>
          <div class="list"><i></i>Comment</div>
          <div class="list"><textarea></textarea></div>
          <div><button><i></i>Cancel</button><button><i></i>AddTask</button></div>
        </div>
      </div>
      <div class="listItem">
        <div class="listTitle">
          <div>
            <span></span>
            <input type="text" placeholder="Type Something Here...">
          </div>
          <div>
            <i>重要</i>
            <i>修改</i>
          </div>
        </div>
        <div class="listContent">
          <div class="list"><i></i>Deadline</div>
          <div class="list"><date></date><date></date></div>
          <div class="list"><i></i>File</div>
          <div class="list">+</div>
          <div class="list"><i></i>Comment</div>
          <div class="list"><textarea></textarea></div>
          <div><button><i></i>Cancel</button><button><i></i>AddTask</button></div>
        </div>
      </div>
      <div class="listItem">
        <div class="listTitle">
          <div>
            <span></span>
            <input type="text" placeholder="Type Something Here...">
          </div>
          <div>
            <i>重要</i>
            <i>修改</i>
          </div>
        </div>
        <div class="listContent">
          <div class="list"><i></i>Deadline</div>
          <div class="list"><date></date><date></date></div>
          <div class="list"><i></i>File</div>
          <div class="list">+</div>
          <div class="list"><i></i>Comment</div>
          <div class="list"><textarea></textarea></div>
          <div><button><i></i>Cancel</button><button><i></i>AddTask</button></div>
        </div>
      </div>
    </main>
    <router-view/>
    <footer>Copyright © 2015 By 提亞 All rights reserved</footer>
  </body>
</template>

<style lang="stylus">
@import 'stylus/normalize'
@import 'stylus/basic'
@import 'stylus/home'
</style>
