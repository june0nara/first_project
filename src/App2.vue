<template>
<div class = "menu">
  <p v-for= "(a,i) in 메뉴들" :key="i">{{i}}</p>
</div>

<!-- <div>
<div v-for = "(a,i) in products" :key="i">
  <h4>{{products[i]}}</h4> 
</div> -->


<!-- key를 꼭 쓰라고 하는 이유, a는 문자를 i는 숫자를 말하며, in앞에 두개까지 쓸 수 있음 -->
<!-- x -->

</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      메뉴들 : ['home', 'shops', 'about'],
      products : ['역삼동원룸', '천호동원롬', '마포구원룸']
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu p {
  color: white;
  padding: 10px;

}
</style>



