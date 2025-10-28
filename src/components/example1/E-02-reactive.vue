<template>
  <div>{{ fullName }}</div>
</template>

<script>
export default {
  // 컴포넌트의 이름을 지정해 주지 않으면 파일의 이름이 기본적으로 사용됨. 다른 곳에서 사용할때 파일의 이름으로 사용해야됨.
  name: "E02Reactive",
  data() {
    return {
      firstName: "Kyungsu",
      lastName: "Lee"
    };
  },
  // H, C, J를 이용해 Rendering을 한뒤 mount함수를 이용해 Rendering을 통해 그려진 거를 화면에 붙임. 이 전체 과정을 vue의 life-style이라 부름.
  mounted() {
    console.log('mounted'); //마운트 함수 실행 됐는지 확인

    let a = 10;
    setTimeout(() => {
      console.log('setTimeout');
      a = 20;
      console.log(a);
    }, 500);

    setTimeout(() => {
      this.lastName = "123";
    }, 1000 );

    setTimeout(() => {
      this.firstName = "KSL"; // 페이지가 렌더링 된 이후 실행되므로 firstname이 이걸로 바뀜.
    }, 2000); //setTimeout이라는 함수는 인자를 2개 받음. callback함수, timeout(ms): 이 시간이 지나면 callback함수가 실행됨. this: script전체.
  },
  //options API에서는 동적인 변수(reactive)를 computed에서 정의, 값이 바뀌게 된다면 렌더링이 다시됨. 마운트는 다시 안됨. . 정적인 변수는 const, var, let같은거 값이 바뀌어도 그게 끝.
  computed: {
    fullName() {
      return this.firstName + " " + this.lastName;
    }
  }
};
</script>
