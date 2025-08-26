<template>
    <p v-if="cnt > 3">재고가 있음:{{ cnt }}</p>
    <p v-else-if="cnt > 0"> 재고가 조금 남음:{{ cnt }}</p>
    <p v-else-if="cnt == 0">재고가 없음:{{ cnt }}</p>
    <p v-else>선불 및 예약 있음:{{ cnt }}</p>
</template>

<script setup>
import { ref } from 'vue';

const cnt = ref(-1)
</script>

<style scoped></style>