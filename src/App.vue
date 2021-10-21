<template>

  <div v-if="모달창열렸니" class="black-bg">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p> 상세페이지 내용임</p>
      <button @click="모달창열렸니= false">닫기</button>
    </div>    
  </div>

  <div class="menu">
    <a v-for="메뉴 in 메뉴들" :key="메뉴"> {{ 메뉴}} </a>
  </div>



  <div v-for="(원룸, i) in 원룸들" :key="원룸" >
    <img :src="원룸들[i].image" class="room-img" alt="">
    <h4 @click="모달창열렸니= true">
      {{ 원룸들[i].title}}
    </h4>
    <p> {{ 원룸들[i].price}} 원</p>
  </div>
  
  
</template>

<script>
import data from './assets/oneroom' 

export default {
  name: 'App',
  data() {
    return {  
      원룸들 : data,
      모달창열렸니: false,    
      메뉴들 : ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }    
  }
}
</script>

<style>
.room-img {
  width: 80%;
  margin-top: 40px;
}
body{
  text-align: center;
  margin: 0;
}

div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, .5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
