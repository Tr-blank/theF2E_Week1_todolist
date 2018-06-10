<template>
  <div class="home">
   <div class="homeHeader">
      <div :class="navThree_now">
        <a :class="nowPage==1? 'homeNavItem now':'homeNavItem'" @click="clickPage" page="1" >My Tasks</a>
        <a :class="nowPage==2? 'homeNavItem now':'homeNavItem'" @click="clickPage" page="2" >In Progress</a>
        <a :class="nowPage==3? 'homeNavItem now':'homeNavItem'" @click="clickPage" page="3">Completed</a>
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
      <div v-for="(list,index) in sortData " :key="index" v-if="test(list)" :class="list.ItemStatus">
        <div class="listTitle">
          <div @click="click_Complete(list)">
            <i class="icon fas fa-check-square"></i>
            <span class="title">{{list.title}}</span>
          </div>
          <div>
            <i @click="click_Important(list)" :class="list.ItemStatus.item_important? 'icon fas fa-star':'icon far fa-star'"></i>
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
  name: 'Original',
  data(){
    return{
      dataJson:[{
        number:1,
        title:'Type Something Here...1',
        ItemStatus: {
          listItem:true,
          item_complete:false,
          item_important:false,
        }
      },{
        number:2,
        title:'Type Something Here...2',
        ItemStatus: {
          listItem:true,
          item_complete:true,
          item_important:false,
        }
      },{
        number:3,
        title:'Type Something Here...3',
        ItemStatus: {
          listItem:true,
          item_complete:false,
          item_important:true,
        }
      },{
        number:4,
        title:'Type Something Here...4',
        ItemStatus: {
          listItem:true,
          item_complete:true,
          item_important:true,
        }
      }],
      nowPage:1,
    }
  },
  created : function () {
    this.dataJson.filter(function(data, index){
      // console.log(data.ItemStatus);
      if(data.ItemStatus.item_complete){data.number += 10000};
      if(!data.ItemStatus.item_important){data.number += 100};
      return data;
    });
  },
  methods: {
    clickPage:function(event){ // `event` 是原生 DOM 事件
        // this.nowPage
        var el = event.currentTarget;//复杂的click哈哈
        this.nowPage = el.getAttribute("page");

        //var el = event.target;//哈哈
    },
    test: function(data) {
        if(this.nowPage == 2 && data.ItemStatus.item_complete == true){
            return false;
        }
        if(this.nowPage == 3 && data.ItemStatus.item_complete == false){
            return false;
        }
        return true;
    },
    click_Complete:function(data){
      data.ItemStatus.item_complete = !data.ItemStatus.item_complete;
      data.ItemStatus.item_complete ? data.number += 10000 : data.number -= 10000;
    },
    click_Important:function(data){
      data.ItemStatus.item_important = !data.ItemStatus.item_important;
      data.ItemStatus.item_important ? data.number -= 100 : data.number += 100;
    }
  },
  computed: {
    navThree_now(){
      if(this.nowPage == 1){
        return "homeNav navThree-now1";
      }else if(this.nowPage == 2){
        return "homeNav navThree-now2";
      }else{
        return "homeNav navThree-now3";
      }
    },
    sortData(){
      return this.dataJson.sort(function sortId(a,b){  
        return a.number-b.number 
      });
    },
  }
}
</script>


<style lang="stylus">
@import '../stylus/basic'
@import '../stylus/home'
</style>
