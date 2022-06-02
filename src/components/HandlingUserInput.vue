<template>
  <h1>{{ message }}</h1>
  <button @click="reverseMessage">Reverse Message</button>
  <button @click="message += '!'">Append "!"</button>
  <!-- -- @click.prevent: 클릭하면 'href' 이벤트를 중지시키고 'notify' 메소드 호출 -- -->
  <a href="https://vuejs.org" @click.prevent="notify">A link with e.preventDefault()</a>
</template>

<script setup>
  import { ref } from 'vue';

  const message = ref('Hello World!');

  function reverseMessage() {
    // -- .split().reverse().join(): 'message.value'를 뒤집기 --
    message.value = message.value.split('').reverse().join('');
  };
  function notify() {
    alert('Navagation was prevented.');
  };
</script>

<style>
  button, a {
    display: block;
    margin-bottom: 1em;
  }
</style>