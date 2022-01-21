// https://www.youtube.com/channel/UCI4tTBupvhMX1aWDSm-HAXw/membership
// => 기초
// https://www.youtube.com/watch?v=qSrBvK0f9Og&list=PLB7CpjPWqHOu6NnQJEGbofB5KO1j2ab9I&index=9
//  => 데이터 베인딩
// 코지 코더
// 프리미엄 멤버십 가입 18,000원(22.1.21)
// 아이디:hblee66@nate.com pass:inxxxx**

<template>
  <div class="name"> {{ nicname }} 만세!!! </div>
  <div> {{greeting()}} !!!</div>
  <div> {{greeting1('청함')}} !!!</div>
  <div> {{greeting1(nicname)}} !!!</div>
  <div> {{greet}} </div>
  <button
    class= "btn btn-primary" @click="updateName"> 
    버튼
  </button>
  <div> {{nicnm[0]}} </div>
</template>

<script>
import { ref } from 'vue';  // string, 숫자, object, array 모두 가능 하지만 반드시 .value를 사용 하여야 된다
import { reactive } from 'vue'; // object, array만 사용 가능하다 .value를 사용하지 않아도 된다

export default {
  setup() {  //vue3
    const nicname = ref("대뿌리");
    const nicnm = reactive(['이','청','함']);

    //함수사용하기
    const greeting = () => {
      return "안녕하세요???"
    }

    const greeting1 = (nicname) => {
      return nicname + "님 반갑습니다"
    }

    //함수를 사용한다
    const greet = greeting1(nicname.value);

    const updateName = () => {
      nicname.value= " ★ ★ ★ ★ ★ ★ ★ ★ ★ ";
      console.log(nicname);
    }

    //리턴값 정의
    return {
      nicname,
      greeting,
      greeting1,
      greet,
      updateName,
      nicnm
    };
  }
}
</script>

<style>
.name{
  color :royalblue
}
.btn{
  margin: 30px;
  width:200px;
}

</style>