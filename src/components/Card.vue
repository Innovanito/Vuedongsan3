<template>
  <div  >
    <img :src="원룸.image" class="room-img" alt="">
    <h4 @click="함수">{{ 원룸.title}}</h4>
    <p @click="함수"> {{ 원룸.price}} 만원임</p>
  </div>
</template>

<script>
export default {
  props: {
    원룸: Object
  },
  methods: {
    함수() {
      this.$emit('openModal', this.원룸.id)
    }
  }
}
</script>

<style>

</style>