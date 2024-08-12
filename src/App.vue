<template>
  <div class="container mt-4">
    <h2 class="text-center mb-4">Calculatrice</h2>

    <div class="form-group mb-3">
      <h3>Choisissez une opération</h3>
      <div class="d-flex flex-column mt-4">
        <input type="radio" id="addition" value="addition" v-model="selectedOperation">
        <label for="addition">Addition</label>

        <input type="radio" id="subtraction" value="subtraction" v-model="selectedOperation">
        <label for="subtraction">Soustraction</label>

        <input type="radio" id="multiplication" value="multiplication" v-model="selectedOperation">
        <label for="multiplication">Multiplication</label>

        <input type="radio" id="division" value="division" v-model="selectedOperation">
        <label for="division">Division</label>
      </div>
    </div>

    <component :is="currentComponent"/>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import Addition from './components/Addition.vue';
import Subtraction from './components/Subtraction.vue';
import Multiplication from './components/Multiplication.vue';
import Division from './components/Division.vue';

const selectedOperation = ref('');

const currentComponent = computed(() => {
  switch (selectedOperation.value) {
    case 'addition':
      return Addition;
    case 'subtraction':
      return Subtraction;
    case 'multiplication':
      return Multiplication;
    case 'division':
      return Division;
    default:
      return null;
  }
});
</script>
