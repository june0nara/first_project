<template>
<div>
<!-- 데이터 바인딩 하는 이유? 하드코딩 하면 나중에 변경 되고 했을 때 가변적인 데이터들은 하드코딩 해놓는거보다 박아 놓는게 더 옳은 방식임 -->
<!-- 데이터 바인딩을 해야할지 말아야할지, 자주 변경하는건 데이터 바인딩, 콧수염 방식으로 -->
<!-- 모든것을 다 박아 놀것인가, class명 같은거 이런것도 박아 놓을 수 있고, 스타일 속성 이런것도 바인딩 가능 -->
<!-- 태그 안에서 데이터 바인딩 할때는 콧수염 안에 넣어야하고, 속성 문법 안에서 할때는 : 하고 하면 됌 <h4 class = "red" : style ="스타일"> -->
<!-- var 어레이 = [10,20,30]; -->

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



