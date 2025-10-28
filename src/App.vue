<!--E01Instance를 받아옴-->
<template>
  <E04Directives/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

//E01Instance를 받아옴
import E04Directives from "@/components/example2/E-04-directives.vue";
export default defineComponent({
  name: 'App',
  components: {
    E04Directives
  }
});
</script>

<style>
</style>
