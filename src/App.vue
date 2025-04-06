<template>
  <main>
    <!-- heading -->
    <header>
      <img src="https://pinia.vuejs.org/logo.svg" alt="pinia logo">
      <h1>Pinia</h1>
    </header>

      <h1>Count is {{ store.count }}</h1>
      <h2>Double is {{ store.doubleCount }}</h2>
      <button @click="store.increment (1)">Increment</button>
      <button @click="store.waitAndAdd">Wait + Increment</button>
  </main>
</template>

<script setup>
import {storeToRefs } from 'pinia'
import { useCounterStore } from "./store/counter";
const store = useCounterStore();
const { count } = storeToRefs(store) // REACTIVE
console.log(count) // => REF
store.count++;
store.increment(2);
</script>
