<template>
  <div v-for ="(a,i) in 원룸들" :key="i">
      <img :src="a.image" class="room-img">
      <h4 @click="모달창열렸니 = true; 누른거 = i">{{a.title}}</h4>
      <p>{{a.price}}원</p>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>