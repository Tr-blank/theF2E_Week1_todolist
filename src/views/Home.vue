<template>
  <div class="home">
   <div class="homeHeader">
      <div class="homeNav navThree-now1">
        <a class="homeNavItem now" page="1" >My Tasks</a>
        <a class="homeNavItem" page="2">In Progress</a>
        <a class="homeNavItem" page="3">Completed</a>
      </div>
    </div>
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
            <span class="title">123132</span>
          </div>
          <div>
            <i v-if="complete" class="icon fas fa-star"></i>
            <i v-else class="icon far fa-star"></i>
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
    <footer>Copyright © 2018 By 提亞 All rights reserved</footer>
  </div>
</template>
<script>
export default {
  name: 'Home',
  data:{

      dataJson:[{
        date:'2018-12-10',
        title:'Type Something Here...',
        important:false,
        complete:false,
        comment:'commentttttttt'
      },
      {
        date:'2018-12-10',
        title:'Type Something Here...',
        important:false,
        complete:false,
        comment:'commentttttttt'
      },
      {
        date:'2018-12-10',
        title:'Type Something Here...',
        important:false,
        complete:false,
        comment:'commentttttttt'
      }],
      complete :false,
      checkedState:true,

  },
  methods: {
  },
  computed: {
  }
}
</script>
<style lang="stylus">
@import '../stylus/basic'
@import '../stylus/home'
</style>
