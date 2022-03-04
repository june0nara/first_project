<template>
<div>
<div v-for = "(a,i) in products" :key="i">
  <h4>{{products[i]}}</h4>
  
</div>

<div class = "menu">
  <p>Home</p>
  <p>Products</p>
  <p>About</p>
  <p>About</p>
  <p>About</p>
  <p>About</p>
</div>

<div>
<h4 v-for = "i in products" :key="i">{{i}}</h4>
</div>

<div class = "menu">
  <p v-for= "i in 3" :key='i'>Home</p>
</div>

<div class = "menu">
  <p v-for= "i in 메뉴들" :key="i">{{i}}</p>
</div>

<div class = "menu">
  <p v-for= "(a,i) in 메뉴들" :key="i">{{i}}</p>
</div>
<!-- key를 꼭 쓰라고 하는 이유, a는 문자를 i는 숫자를 말하며, in앞에 두개까지 쓸 수 있음 -->

  <h4>{{products[1]}} 원룸</h4>
  <p> 60 만원</p>
</div>

<div>
  <h4>{{products[2]}}  원룸</h4>
  <p> 70 만원</p>
</div> 

<div>
  <h4>{{products[0]}}  원룸</h4>
  <p> 70 만원</p>
</div> 

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



