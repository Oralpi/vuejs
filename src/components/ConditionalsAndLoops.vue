<template>
  <button @click="show = !show">Toggle List</button>
  <!-- -- list.push(list.length + 1): 'list'의 'list.length'에 '+= 1'씩 배열 추가 -- -->
  <button @click="list.push(list.length + 1)">Push Number</button>
  <!-- -- list.pop(): 'list'에서 배열 삭제 -- -->
  <button @click="list.pop()">Pop Number</button>
  <!-- -- list.reverse(): 'list'의 배열을 거꾸로 -- -->
  <button @click="list.reverse()">Reverse List</button>
  <ul v-if="show && list.length">
    <li v-for="item of list">{{ item }}</li>
  </ul>
  <p v-else-if="list.length">List is not empty, but hidden.</p>
  <p v-else>List is empty.</p>
</template>

<script setup>
import { ref } from 'vue';

const show = ref(true);
const list = ref([1, 2, 3]);
</script>

<style>

</style>