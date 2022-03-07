
<template>
<!-- 
<div class = "black-bg" v-if="모달창열렸니 == true">
  <div class = "white-bg">
  <h4>{{원룸들[누른거].title}}</h4>
  <p>상세페이지 내용임</p>
  <button @click = "모달창열렸니 = false">닫기</button>
  </div>
</div> -->


<div class = "menu">
  <a v-for= "a in 메뉴들" :key="a">{{a}}</a>
</div>

<!-- 
<div v-for= "(a,i) in 원룸들" :key="i">
  <img :src= "원룸들[누른거].image" class = "room-img">

  <h4 @click = "모달창열렸니 = true; 누른거 = i">{{원룸들[i].title}}</h4>
  <p>{{원룸들[i].price}}원</p>
</div> -->

<Card :원룸="원룸들[0]"/>
<Card :원룸="원룸들[1]"/>
<Card :원룸="원룸들[2]"/>
<Card :원룸="원룸들[3]"/>
<Card :원룸="원룸들[4]"/>
<Card :원룸="원룸들[5]"/>



</template>

<script>
import data from './oneroom.js' ;
// import Modal from './Modal.vue' ;
import Card from './Card.vue' ;

export default {
  name: 'App',
  data(){
    return {
      // 모달창열렸니 : Modal,
      누른거 : 0,
      원룸들 : data,
      메뉴들 : ['home', 'shops', 'about'],
      products : ['역삼동원룸', '천호동원롬', '마포구원룸']
    }
  },
  components: {
    // Discount : Discount,
    // Modal : Modal,
    Card : Card,
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1e2c3a;
  margin-top: 60px;
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



