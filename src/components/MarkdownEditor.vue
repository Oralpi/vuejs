<template>
  <div class="editor">
    <!-- -- :value, @input: script의 'input', 'update'의 값을 핸들링(v-model 사용 X) -- -->
    <textarea class="input" :value="input" @input="update"></textarea>
    <!-- -- v-html: html코드를 template에 직접 넣어줌 -- -->
    <div class="output" v-html="output"></div>
  </div>
</template>

<script setup>
import { marked } from 'marked';
import { debounce } from 'lodash-es';
import { ref, computed } from 'vue';

const input = ref('# hello');
// -- computed(): 여기에 정의한 함수는 반드시 값을 리턴 --
// -- marked(): markdown을 html 형식으로 변경 --
const output = computed(() => marked(input.value));
// -- debounce(): 'e' 함수가 호출될때 가장 마지막이나 가장 처음의 1회만 이벤트 발생 --
const update = debounce((e) => {
  // -- e.target.value: 특정 이벤트가 발생하는 '<textarea>' 태그를 가르킴--
  input.value = e.target.value;
});
</script>

<style>
  body {
    margin: 0;
  }

  .editor {
    height: 100vh;
    display: flex;
  }

  .input, .output {
    overflow: auto;
    width: 50%;
    height: 100%;
    box-sizing: border-box;
    padding: 0 20px;
  }

  .input {
    border: none;
    border-right: 1px solid #ccc;
    resize: none;
    outline: none;
    background-color: #f6f6f6;
    font-size: 14px;
    font-family: 'Monaco', courier, monospace;
    padding: 20px;
  }

  code {
    color: #f66;
  }
</style>