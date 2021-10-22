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
  methods: {
    
  }
}
</script>

<style>

</style>