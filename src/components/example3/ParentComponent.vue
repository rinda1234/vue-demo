<!-- ParentComponent.vue -->
<template>

<!--  컴포넌트를 vue로 만들어서 재활용가능. 컴포넌트를 가져와서 씀. 내 컴포넌트안에.-->
<!--  부모에서 자식으로 넘어가는거: property, 자식이 부모에게 이벤트 발생 전달. : Emit-->
  <div>
    <!-- 부모에서  property 활용 ':' , emit 활용 '@'-->
    <!--custom enent가 실행이 된다면 handleEvent 함수가 실행됨. -->
    <ChildComponent
        :message="parentMessage"
        :id = "1"
        :password = "1234"
        @custom-event="handleEvent"
    />
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  name: "E05ParentComponent",
  data() {
    return {
      parentMessage: 'Hello from parent'
    };
  },
  methods: {
    handleEvent(payload) {
      console.log(payload); //emit을 통해 같이 받은 데이터가 payload에 들어감. event가 발생했을때
    }
  },
  components: {
    ChildComponent
  }
};
</script>
