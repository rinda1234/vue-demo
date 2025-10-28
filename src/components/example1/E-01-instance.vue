<template>
<!--  중괄호 안에 script안의 변수가 들어있음. 여기를 렌더링 하게 되면 <div>Hello, vue!</div> 가됨-->
  <div>Hello, {{ message }}</div>
</template>

<script>
export default {
  name: "E01Instance",
  // 이렇게 함수를 이용해 변수를 리턴하게 되면 이 변수를 위 HTML테그에서도 사용가능
  data() {
    // 이런식으로 이름을 넣어줄 수 있음.
    const name = 'LeeDaebok'
    return {
      message: name
    };
  }
};
</script>

<style scoped>
div {
  color: blue;
  font-size: 20px;
  font-weight: bold;
}
</style>
