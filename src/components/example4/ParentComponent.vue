<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent1 />
  </div>
</template>

<script>

import ChildComponent1 from "@/components/example4/ChildComponent1.vue";

export default {
  name: "E06ParentComponent",
  // 컴포넌트의 계층이 깊어지면 깊어질수로 property로 일일히 보내는건 낭비가 되기 때문에 provide를 이용해서 보냄.
  // 모든 자식컴포넌트들이 이용할 수 있게됨. inject를 이용해 받음
  provide() {
    return {
      sharedMessage: 'Hello from provide'
    };
  },
  components: {
    ChildComponent1
  }
};
</script>
