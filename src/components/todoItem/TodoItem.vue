<template>
  <li>{{ todo.text }}</li>
</template>

<script setup>
// -- const props = defineProps({}): 속성 이름과 타입을 포함하는 오브젝트로 선언 --
const props = defineProps({
  // -- Object: 객체({}) --
  todo: Object
});
</script>

<style>

</style>