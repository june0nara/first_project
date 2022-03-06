<template>
  <div v-for ="(a,i) in 원룸들" :key="i">
      <img :src="a.image" class="room-img">
      <h4 @click="모달창열렸니 = true; 누른거 = i">{{a.title}}</h4>
      <p>{{a.price}}원</p>
  </div>
</template>

<script>
export default {
    name : 'card'

}
</script>

<style>

</style>

<template>
  <div>
    <img :src="원룸.image" class="room-img">
    <h4> {{원룸.title}} </h4>
    <p>{{원룸.price}} 원</p>
   </div>
</template>


<script>
export default {
  props : {
    원룸 : Object
  }
}
</script>

