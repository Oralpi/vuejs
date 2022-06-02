<template>
  <h2>Text Input</h2>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input v-model="text"> {{ text }}
  <h2>Checkbox</h2>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input type="checkbox" id="checkbox" v-model="checked">
  <label for="checkbox">Checked: {{ checked }}</label>
  <h2>Multi Checkbox</h2>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
  <label for="jack">Jack</label>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input type="checkbox" id="john" value="John" v-model="checkedNames">
  <label for="john">John</label>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
  <label for="mike">Mike</label>
  <!-- -- <pre>: HTML 입력한 형태 그대로 보여줌 -- -->
  <p>Checked names: <pre>{{ checkedNames }}</pre></p>
  <h2>Radio</h2>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input type="radio" id="one" value="One" v-model="picked">
  <label for="one">One</label>
  <br>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <input type="radio" id="two" value="Two" v-model="picked">
  <label for="two">Two</label>
  <br>
  <span>Picked: {{ picked }}</span>
  <h2>Select</h2>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <select v-model="selected">
    <!-- -- <option disabled>: '<option>' 요소를 비활성화 -- -->
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ selected }}</span>
  <h2>Multi Select</h2>
  <!-- -- v-model: 입력 값이 자동으로 연결 -- -->
  <!-- -- <select multiple>: <select> 요소에 둘 이상의 값을 입력 -- -->
  <select multiple style="width: 100px;" v-model="multiSelected">
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ multiSelected }}</span>
</template>

<script setup>
import { ref } from 'vue';

const text = ref('Edit me');
const checked = ref(true);
const checkedNames = ref(['Jack']);
const picked = ref('One');
const selected = ref('A');
const multiSelected = ref(['A']);
</script>

<style>

</style>