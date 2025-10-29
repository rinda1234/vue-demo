<template>
  <div class="container">
<!--  vue에는 반복문이나 조건문을 이용해서 vue를 띄우는것을 관리할 수 있음 v-if 같은 걸로., -->
    <ul>
<!--  반복문 문법 li: 리스트를 띄움, items안의 item들을 모두 순회하여 출력. -->
      <li v-for="item in items" :key="item.id">
        {{ item.name }} - {{ item.id }}
      </li>
    </ul>

    <div>
<!-- 3개다 숨길 수 값에 따라 숨기고 띄움. -->
<!-- if 조건부 렌더링, isvisible이 true이면 dom에 생성, 조건 만족시에만 dom에 존재. 레이아웃 제거됨.    -->
      <div v-if="isVisible">This is visible 1</div>
<!-- visibility이라는스타일을 visible로 할지 hidden으로 할지 isvisible에 따라 정함.  true이면 보이고 false 이면 안보이게. dom은 항상존재. 레이아웃 유지. -->
      <div :style="{ visibility: isVisible ? 'visible' : 'hidden' }">
        This is visible 2
      </div>
<!--    dom은 항상 존재. 레이아웃 제거. 반복적으로 숨김/ 보임이 필요한 경우 좋음.   -->
      <div v-show="isVisible">This is visible 3</div>
<!--      클릭할때마다 isvisible값 변경-->
      <button @click="isVisible = !isVisible">Toggle Visibility</button>
    </div>

    <div>
<!--       변수출력-->
      <div v-text="count"></div>
<!--   "" 안의 text를 html로 바꿔서 출력   -->
      <div v-html="`<strong>${count}</strong>`"></div>
<!--   중괄호 안의 text를 script와 연동안하고 그대로출력   -->
      <div v-pre>{{ count }}</div>
<!-- 조건문들 .조건이 맞으면 출력, dom 생성 x-->
      <div v-if="count % 3 === 0"> count % 3 === 0</div>
      <div v-else-if="count % 2 === 0"> count % 2 === 0</div>
      <div v-else>Count is not divisible by 2 or 3</div>

      <div id = "div-1" v-if="count % 3 === 0"> count % 3 === 0</div>
      <div id = "div-2" v-else-if="count % 2 === 0"> count % 2 === 0</div>
      <div id = "div-4" v-else-if="count % 5 === 0"> count % 5 === 0</div>
      <div id = "div-3" v-else>Count is not divisible by 2 or 3</div>

      <button @click="count++">Increment Count</button>
    </div>

  </div>

<!--
 directives
 1. v-if
 2. v-else
 3. v-else-if
 4. v-show
 5. v-for
 6. v-on
 7. v-bind
 8. v-model
 9. v-slot
10. v-text
11. v-html
12. v-pre
13. v-cloak
14. v-once
15. v-is
16. v-memo
 -->
</template>

<script>
export default {
  name: "E04Directives",
  data() {
    return {
      isVisible: true,
      items: [
        { id: 1, name: "Item 1" },
        { id: 2, name: "Item 2" },
        { id: 3, name: "Item 3" },
        { id: 4, name: "Item 4" },
      ],
      count: 0,
    };
  }
};
</script>

<style scoped>
.container {
  display: grid;
  width: 300px;
  margin: 0 auto;
  padding: 20px;
  grid-gap: 20px;

}
</style>
