<template>
  <div>
    <p>Name: {{ person.name }}</p>
    <p>Age: {{ person.age }}</p>
    <button @click="incrementAge">Increment Age</button>
  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  name: 'E11Reactive',
  setup() {
    //reactive 에는 복합적인 자료, 딕셔너리 같은게 들어갈 수 있음., ref는 단일값
    const person = reactive({
      name: 'John Doe',
      age: 30
    });

    const incrementAge = () => {
      person.age++; // reactive는 바로 속성에 접근
    };

    return {
      person,
      incrementAge
    };
  }
};
</script>
