<template>
  <ol>
    <!-- -- :todo="item": 'item'을 'TodoItem.vue'의 'todo'에 넣음 -- -->
    <TodoItem v-for="item in groceryList" :todo="item" :key="item.id"></TodoItem>
  </ol>
</template>

<script setup>
import { ref } from 'vue';
import TodoItem from './components/todoitem/TodoItem.vue';

const groceryList = ref([
  {
    id: 0,
    text: 'Vegetables'
  },
  {
    id: 1,
    text: 'Cheese'
  },
  {
    id: 2,
    text: 'Whatever else humans are supposed to eat'
  }
]);
</script>

<style>

</style>