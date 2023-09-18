<script setup>
import { reactive } from 'vue';
import Calculadora from './components/Calculadora.vue'

const state = reactive({
  result: 0,
  num1: 0,
  num2: 0,
  operator: '+'
});

const calc = () => {
  switch (state.operator) {
    case '+':
      state.result = +state.num1 + +state.num2
      break;
    case '-':
      state.result = +state.num1 - +state.num2
      break;
    case '/':
      state.result = +state.num1 / +state.num2
      break;
    case '*':
      state.result = +state.num1 * +state.num2
      break;
  }
}

const getNumber = e => {
  if (e.target.id == 'num1') {
    state.num1 = e.target.value;
  } else {
    state.num2 = e.target.value
  }
  calc();
}

const getOperator = e => {
  state.operator = e.target.value;
  calc();
}

</script>

<template>
  <div class="container">
    <h1>Calculadora</h1>
    <Calculadora :result="state.result" :get-number="getNumber" :get-operator="getOperator" />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
  font-weight: bold;
  color: #424242;
}

.container {
  width: 1024px;
  max-width: 100%;
  margin: 0 auto;
  text-align: center;
  margin-top: 150px;
  padding: 20px;
  background-color: #e6e6e6;
  border-radius: 5px;
}

.container h1 {
  font-size: 32px;
  margin-bottom: 20px;
  text-transform: uppercase;
}
</style>
