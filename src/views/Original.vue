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
      <div :class="addOpen? 'addItem addItem-open':'addItem'" v-if="nowPage!=3">
        <div class="addTitle">
          <div class="addButton" @click="addItem_open" v-if="!addOpen">
            <i class="fas fa-plus"></i>Add Task
          </div>
          <div v-if="addOpen">
            <i class="icon fas fa-check-square"></i>
            <input class="title" type="text" v-model="addItem_data.title">
          </div>
          <div v-if="addOpen">
            <i :class="addItem_data.ItemStatus.item_important? 'icon fas fa-star':'icon far fa-star'"></i>
            <i @click="addItem_open" class="icon fas fa-pencil-alt"></i>
          </div>
        </div>
        <ul class="listContent">
          <li class="listContentLine"><i class="far fa-calendar-alt"></i><span class="listContentTitle">Deadline</span>
            <input class="deadline_date" type="date" v-model="addItem_data.itemDate">
            <input class="deadline_time" type="time" v-model="addItem_data.itemTime">
          </li>
          <li class="listContentLine">
            <i class="far fa-file"></i>
            <span class="listContentTitle">File</span>
            <span class="uploadFile">
              <span  v-if="addItem_data.fileTime != '' && addItem_data.fileName != ''">{{addItem_data.fileName}}<span class="fileInfo">{{addItem_data.fileTime}}</span></span>
              <label for="uploadFile">
                <i class="fas fa-plus-square"></i>
                <input class="hide" type="file" id="uploadFile" @change="fileSelected">
              </label>              
            </span>
          </li>
          <li class="listContentLine"><i class="far fa-comment-dots"></i><span class="listContentTitle">Comment</span><textarea placeholder="Type your memo here…"></textarea></li>
          <li>
            <button @click="addItem_open" class="buttonCancel"><i class="fas fa-times"></i>Cancel</button>
            <button class="buttonMain"><i class="fas fa-plus"></i>Add Task</button>
          </li>
        </ul>
      </div>
      <div v-for="(list,index) in sortData " :key="index" v-if="pageChange(list)" :class="list.ItemStatus">
        <div class="listTitle">
          <div class="listTitle-info">
            <i class="icon fas fa-check-square" @click="click_Complete(list)" ></i>
            <div class="title">
              <span v-if="!list.ItemStatus.item_modify">{{list.title}}</span>
              <input v-if="list.ItemStatus.item_modify" class="title" type="text" v-model="list.title">
              <div v-if="!list.ItemStatus.item_complete" class="title-icons">
                <i class="far fa-calendar-alt"  v-if="list.itemDate != ''"></i>{{list.itemDate}}
                <i class="far fa-file" v-if="list.fileName != ''"></i>
                <i class="far fa-comment-dots"  v-if="list.comment != ''"></i>
              </div>
            </div>
          </div> 
          <div>
            <i @click="click_Important(list)" :class="list.ItemStatus.item_important? 'icon fas fa-star':'icon far fa-star'"></i>
            <i @click="click_Modify(list)" class="icon fas fa-pencil-alt"></i>
          </div>
        </div> 
        <ul class="listContent">
          <li class="listContentLine"><i class="far fa-calendar-alt"></i><span class="listContentTitle">Deadline</span>
            <input class="deadline_date" type="date" v-model="list.itemDate">
            <input class="deadline_time" type="time" v-model="list.itemTime">
          </li>
          <li class="listContentLine">
            <i class="far fa-file"></i>
            <span class="listContentTitle">File</span>
            <span class="uploadFile">
              <span  v-if="list.fileTime != '' && list.fileName != ''">{{list.fileName}}<span class="fileInfo">{{list.fileTime}}</span></span>
              <label for="uploadFile">
                <i class="fas fa-plus-square"></i>
                <input class="hide" type="file" id="uploadFile">
              </label>              
            </span>

          </li>
          <li class="listContentLine"><i class="far fa-comment-dots"></i><span class="listContentTitle">Comment</span><textarea v-model="list.comment" placeholder="Type your memo here…"></textarea></li>
          <li>
            <button @click="click_Modify(list)" class="buttonCancel"><i class="fas fa-times"></i>Cancel</button>
            <button class="buttonMain"><i class="fas fa-plus"></i>Save</button>
          </li>
        </ul>
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
          item_modify:true,
        },
        itemDate:'2018-06-06',
        itemTime:'18:00',
        fileTime:'2018.png',
        fileName:'2018-06-06',
        comment:'一些內容...1'
      },{
        number:2,
        title:'Type Something Here...2',
        ItemStatus: {
          listItem:true,
          item_complete:true,
          item_important:false,
          item_modify:false,
        },
        itemDate:'2018-06-06',
        itemTime:'18:00',
        fileTime:'2018.png',
        fileName:'2018-06-06',
        comment:'一些內容...2'
      },{
        number:3,
        title:'Type Something Here...3',
        ItemStatus: {
          listItem:true,
          item_complete:false,
          item_important:true,
          item_modify:false,
        },
        itemDate:'2018-06-06',
        itemTime:'18:00',
        fileTime:'',
        fileName:'',
        comment:'一些內容...3'
      },{
        number:4,
        title:'Type Something Here...4',
        ItemStatus: {
          listItem:true,
          item_complete:true,
          item_important:true,
          item_modify:false,
        },
        itemDate:'2018-06-06',
        itemTime:'18:00',
        fileTime:'2018.png',
        fileName:'2018-06-06',
        comment:''
      },{
        number:4,
        title:'Type Something Here...5',
        ItemStatus: {
          listItem:true,
          item_complete:true,
          item_important:true,
          item_modify:false,
        },
        itemDate:'2018-06-06',
        itemTime:'18:00',
        fileTime:'',
        fileName:'',
        comment:''
      }],
      addOpen:false,
      addItem_data:{
        title:'Type Something Here...',
        ItemStatus: {
          listItem:true,
          item_complete:false,
          item_important:false,
          item_modify:false,
        },
        itemDate:'',
        itemTime:'',
        fileTime:'',
        fileName:'',
        comment:''
      },
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
    pageChange: function(data) {
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
    },
    click_Modify:function(data){
      data.ItemStatus.item_modify = !data.ItemStatus.item_modify;
    },
    addItem_open(){
      this.addOpen = !this.addOpen;
    },
    addItem_Important(){
      this.addItem_data.ItemStatus.item_important = !this.addItem_data.ItemStatus.item_important;
    },
    fileSelected(evt){
      const file = evt.target.files.item(0);
      console.log(file.name);
      this.addItem_data.fileName = file.name;
      this.addItem_data.fileTime = file.lastModifiedDate;
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
