<script setup>
import { ref } from 'vue';
import D1_bind from './components/D1_bind.vue';
import D2_if from './components/D2_if.vue';
import D3_show from './components/D3_show.vue';
import D4_for from './components/D4_for.vue';
import D5_event from './components/D5_event.vue';


//컴포넌트 맵
const pages = { D1_bind, D2_if, D3_show, D4_for,D5_event }
const activeComp = ref('D5_event')

</script>

<template>
  <!-- <D1_baind /> -->
  <!-- <D2_if /> -->
  <!-- <D3_show /> -->
  <!-- // display : none의 역활 -->
  <!-- <D4_for /> -->
  <!-- <D5_event /> -->
  <!-- 버튼클릭시 보여줄 컴포넌트 -->
  <button @click="activeComp = 'D1_bind'">V-BIND 변수 정의 사용하겠다</button>
  <button @click="activeComp = 'D2_if'">V-IF 조건 분기바인트</button>
  <button @click="activeComp = 'D3_show'">V-SHOW 보이다/감추다</button>
  <button @click="activeComp = 'D4_for'">V-FOR ~동안 실행하다</button>
  <button @click="activeComp = 'D5_event'">V-EVENT 이벤트 발생</button>

  <div class="page-view">

    <KeepAlive>
      <component :is="pages[activeComp]"></component>
    </KeepAlive>

  </div>

  <!-- 니가 보여주는 component가 초기화 0이 되지 않아야한다 -->


</template>


<style scoped>
.page-view {
  margin: 20px;
  border: 3px dashed greenyellow;
  background-color: rgb(182, 208, 233);
}
</style>