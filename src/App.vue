<template>

  <div class="start" :class="{ end : 모달창열렸니 }" >
    <Modal :모달창열렸니="모달창열렸니" :누른거="누른거" 
    :원룸들="원룸들" @closeModal="모달창열렸니 = false" />
  </div>

  <div class="menu">
    <a v-for="메뉴 in 메뉴들" :key="메뉴"> {{ 메뉴}} </a>
  </div>

  <Discount v-if="showDiscount" />
  
  <button @click="priceSort">가격순 정렬</button>
  <button @click="sortBack">되돌리기</button>

  <Card @openModal="모달창열렸니 = true; 누른거 = $event" 
  :원룸="원룸들[i]" v-for="(원룸,i) in 원룸들" :key="원룸" />
  
  
  
</template>

<script>
import data from './assets/oneroom' 
import Discount from './components/Discount.vue'
import Card from './components/Card.vue'
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  data() {
    return {  
      showDiscount : true,
      원룸들오리지널 : [...data],
      누른거 : 0,
      원룸들 : data,
      모달창열렸니: false,    
      메뉴들 : ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }    
  },
  components: {
    Discount,
    Card,
    Modal
  },
  methods: {
    priceSort() {
      this.원룸들.sort(function(a,b) {
        return a.price - b.price
      })
    },
    sortBack() {
      this.원룸들 = [...this. 원룸들오리지널];

    } 
  },
  
  
}
</script>

<style>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 4px;
}
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
.start {
  opacity: 0;
  transition: all 2s;
}
.end {
  opacity: 1;
}
</style>
