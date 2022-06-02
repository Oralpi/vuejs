<template>
  <p>
    <!-- -- :title: 마우스를 올리면 'message'가 보임 -- -->
    <span :title="message">Hover your mouse over me for a few seconds to see my dynamically bound title!</span>
  </p>
  <!-- -- :class: 'red'라는 클래스명을 추가하여, 'isRed'가 'true' 혹은 'false' 확인 -- -->
  <p :class="{ red: isRed }" @click="toggleRed">This should be red... but click me to toggle it.</p>
  <!-- -- :style: 태그 속성에 'color'라는 스타일을 바로 반영 -- -->
  <p :style="{ color }" @click="toggleColor">This should be green, and should toggle between green and blue on click.</p>
</template>

<script setup>
  import { ref } from 'vue';

  const message = ref('Hello World!');
  const isRed = ref(true);
  const color = ref('green');

  function toggleRed() {
    isRed.value = !isRed.value;
  };
  function toggleColor() {
    color.value = color.value === 'green' ? 'blue' : 'green';
  };
</script>

<style>
  .red {
    color: red;
  }
</style>