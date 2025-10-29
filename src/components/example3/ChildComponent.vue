<!-- ChildComponent.vue -->
<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ id }}</p>
    <p>{{ password }}</p>
<!--    emit으로 부모에게 이벤트 전달. 부모에서 @로 emit활용-->
<!--  첫번째 인자. 이벤트의 이름, 두번째 인자 인벤트에 전달할 data   -->
     <button @click="$emit('custom-event', 'Hello from child')">Send Event</button>
  </div>
</template>

<script>
export default {
  // data가 아닌 이유, props는 부모로부터 받은 데이터를 정의해둔 파트. 부모로부터 자식이 받은 property는 prop에 저장되며 자식이 수정 불가.
  props: ['message', "id", "password"],


};
</script>
