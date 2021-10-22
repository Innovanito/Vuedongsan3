<template>
  <div v-if="모달창열렸니" class="black-bg">
    <div class="white-bg">
      <h4>위치: {{ 원룸들[누른거].title}}</h4>
      <p> 설명: {{ 원룸들[누른거].content}}</p>
      <p> <input v-model.number = "month"> 개월 거주 예정</p>
      <p>{{ month }} 개월 선택함 :  {{원룸들[누른거].price * month }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>    
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data() {
    return {
      month: 1,
    }
  },
  props: {
    원룸들 : Array,
    누른거 : Number,
    모달창열렸니 : Boolean,
  },
  watch: {  
    month(a) {
      if( a > 12) {
        alert('13이상 입력하지 마셈')
      } 
      else if ( isNaN(a) == true) {
        alert('문자는 입력하지 마세욤');
        this.month = 1;
      }
    }
  },
  beforeUpdate() {
    if(this.month == 2) {
      alert('2개월은 너무 적음 안팜!')
    }
  }
}
</script>

<style>

</style>