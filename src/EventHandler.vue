<template>

<!-- 모달창 ui를 미리 만들어놔야 뛰우루수 있어 -->

<Modal :원룸들 = "원룸들" :누른거 = "누른거" :모달창열렸니 = "모달창열렸니" />
<!-- :콜론이 = v-bind랑 같은거야, html 데이터 묶을때도 쓰지만 데이터 전송에도 쓰인다 -->


<div class = "menu">
  <p>Home</p>
  <p>Products</p>
  <p>About</p>
</div>


<div class = "menu">
  <p v-for= "(a,i) in 메뉴들" :key="i">{{i}}</p>
</div>
<!-- key를 꼭 쓰라고 하는 이유, a는 문자를 i는 숫자를 말하며, in앞에 두개까지 쓸 수 있음 -->




<Discount/>

<div v-for = "(작명,i) in 원룸들" :key='i'>
  <img :src="원룸들[i].image" class="room-img">
  <h4 @click = "모달창열렸니 = true; 누른거 = i">{{원룸들[i].title}} 원룸</h4>
  <p> {{원룸들[i].price}}</p>
</div>
<Modal></Modal>
<!-- 모달(자식)이 부모 컴퍼넌트가 갖고 있는 데이터를 쓰고 싶다면 props로 데이터 전송해야함  -->




<div>
  <img src = "./assets/logo.png"> 
  <h4 @click = "모달창열렸니 = true">{{원룸들[0].title}} 원룸


    
  </h4>
  <p> {{원룸들[0].price}}</p>
  <button @click ="신고수[0]+=1">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
</div>
<!-- ++는 어떤 변수에다가 1 더해주라는 뜻. +1로 하면 안된다 +=1 -->

<div>
  <h4>{{products[2]}}  원룸</h4>
  <p> 70 만원</p>
  <button @mouseover ="신고수[1]+=1">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
</div> 

<div>
  <h4>{{products[0]}}  원룸</h4>
  <p> 70 만원</p>
  <button @mouseover ="신고수[2]+=1">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
</div> 

</template>

<script>

import data from './oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';


export default {
  name: 'App',
  data(){
    return {
      누른거 : 0,
      원룸들 : data,
      모달창열렸니 : false,
      // 모달창만드는과정1, 모달창이 현재 열렸는지 닫혔는지 모달창에 현재 상태를 먼저 정의해주어야해 true false / 0 1
      신고수 : [0,0,0],
      메뉴들 : ['home', 'shops', 'about'],
      products : ['역삼동원룸', '천호동원롬', '마포구1룸']
    }
  },

  methods : {
    increase1(){
      this.신고수[0] += 1;
      }, 
    increase2(){
      this.신고수[1] += 1;
      },
    increase3(){
      this.신고수[2] += 1;
      }, 
    },
   components: {
      Discount : Discount,
      Modal : Modal,
    }
  }
  // 이거 신고수 += 1 그대로 돌리면 에러 난다, 신고수 정의해달라고 계속 에러남, 함수안에서 데이터 쓸땐(신고수, 메뉴들, products 쓰고 싶으면 무조건 this 써줘야해) this.데이터명

</script>

<style>
/* #app {
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

} */

body {
  margin : 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;

}
/* 아무거나 컴포넌트로 축약하는거 좋치 안 */
</style>
