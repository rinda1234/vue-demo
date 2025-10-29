<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName" placeholder="Last Name" />
    <button @click="greet">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script>
// 이렇게 키 방식으로(name, props, data,) 하는걸 options API라 부름.
export default {
  name: 'E07OptionsApi',
//props: ['title1'] 이런식으로 쓰기도 하고 아래처럼 딕셔너리 형태로 쓰기도 함.
  props: {
    title: {
      type: String,
      default: 'User Information'
    }
  },
// 사용할변수들
  data() {
    return {
      firstName: 'John',
      lastName: 'Doe',
      greetCount: 0,
      message: ''
    };
  },
//변수들을 조합해서 사용. 동적변수
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    }
  },
// 이 컴포넌트에서 사용할 함수들 정의
  methods: {
    greet() {
      this.greetCount++;
      this.message = `Hello, ${this.fullName}!`;
    },
    resetGreetCount() {
      this.greetCount = 0;
    }
  },
// 계속 모니터링 하면서 확인
  watch: {
    greetCount(newValue, oldValue) {
      console.log(`Greet count changed from ${oldValue} to ${newValue}`);
      if (newValue >= 3) {
        this.message = "That's enough greetings for now!";
      }
    }
  },
// life style에 따른 시점 함수들.
  beforeCreate() {
    console.log('beforeCreate hook');
  },

  created() {
    console.log('created hook');
  },

  beforeMount() {
    console.log('beforeMount hook');
  },

  mounted() {
    console.log('mounted hook');
  },

  beforeUpdate() {
    console.log('beforeUpdate hook');
  },

  updated() {
    console.log('updated hook');
  },

  beforeUnmount() {
    console.log('beforeUnmount hook');
  },

  unmounted() {
    console.log('unmounted hook');
  }
};
</script>
