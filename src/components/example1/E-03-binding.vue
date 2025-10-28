<template>
  <div>
<!--    이 input이 message와 연동 되어 있어. input을 바꾸면 message가 바뀜. 변수가 바뀌므로 렌더링이 다시됨. -->
    <input v-model="id" />
    <input v-model="password" />
    <p>{{ message }}</p>
<!--   출력 하는법, whoami라는 이름을 가진 버튼을 하나 생성-->
    <button @click="() => {
      this.message = this.id + ' ' + this.password;
    }">whoami</button>
  </div>
</template>

<script>
export default {
  name: "E03Binding",
  data() {
    return {
      message: "Hello Vue",
      id: "",
      password: ""
    };
  }
};
</script>
