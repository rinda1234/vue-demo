<template>
  <div>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>

<script>
// composition api에서 변수를 어떻게 만드냐
import { ref } from 'vue';

export default {
  name: 'E10Ref',
  setup() {
    const count = ref(0); // ref로 원시 값 생성
    // js 에서는 함수를 변수에 넣을 담을 수 있음.
    const increment = () => {
      count.value++; // ref는 .value를 통해 값을 접근
    };
    // 리턴한것들만 위 html에서 쓸 수 있음.
    return {
      count,
      increment
    };
  }
};
</script>
