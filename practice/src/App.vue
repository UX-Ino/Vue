<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>상세</h4>
      <p>상세</p>
      <button @click="modal=false">닫기</button>
    </div>
  </div>

<div class="menu">
  <!-- <a>Home</a>
  <a>About</a>
  <a>Etc</a> -->
<a v-for="(menuTit, i) in menulist" :key="i">{{menuTit}}</a>
</div>
  <div v-for="(room, i) in roomList" :key="i">
    <img :src="roomList[i].image" alt="" class="room-img">
    <h4>{{roomList[i].title}}</h4>
    <p>{{roomList[i].price}} 만원</p>
  </div>
  <!-- <div>
    <img :src="roomList[0].image" alt="" class="room-img">
    <h4>{{roomList[0].title}}</h4>
    <p>{{roomList[0].price}} 만원</p>
  </div> -->



</template>

<script>
import roomData from './room.js'

export default {
  name: 'App',
  data(){
    return{
       num: [0, 0, 0],
       products : ['역삼동 원룸','천호동 원룸', '신림동 원룸'],
       menulist : ['Home','Shop','Etc'],
       modal : false,
       roomList : roomData,
    }
  },
  methods:{

  },
  components: {
    
    
  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
#app {
  font-family:Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: #fff;
  padding: 15px;
}
.room-img{
  width: 100%;
  margin-top: 40px;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: #fff;
  padding: 20px;
  border-radius: 8px;
}

</style>
