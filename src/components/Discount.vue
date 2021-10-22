<template>
  <div class="discount">
    지금 가입하면 {{amount}}% 할인
  </div>
</template>

<script>
export default {
  data() {
    return {
      amount : 30
    }
  },
  mounted() {
    setInterval(() => {
      this.amount--;
    }, 1000);
  }

}
</script>

<style>

</style>