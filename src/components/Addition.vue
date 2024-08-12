<template>
  <div>
    <h4>Addition</h4>
    <input v-model.number="num1" type="number" placeholder="Nombre 1" class="form-control mb-2" />
    <input v-model.number="num2" type="number" placeholder="Nombre 2" class="form-control mb-2" />
    <button @click="calculate" class="btn btn-primary">Calculer</button>
    <p v-if="result !== null" class="mt-2">Résultat: {{ result }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const result = ref(null);

const calculate = () => {
  result.value = num1.value + num2.value;
};
</script>
