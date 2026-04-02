<!-- ---- SCRIPT ---- -->
<script setup>

// ---- IMPORTS ----
import { ref, computed } from 'vue'

// ---- DATA ----
const celsiusNumber = ref(0)

// ---- COMPUTED ----
const fahrenheit = computed(() => {
    return (celsiusNumber.value * 9/5) + 32
})

</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- TEMPLATE ---- -->
<template>
    <div class="home">
        <div class="card">
            <span class="title">Mudando de Celsius para Fahrenheit</span>
            <input v-model.number="celsiusNumber" type="number" placeholder="Digite °C">
            <span class="resposta">Convertendo: {{ fahrenheit }}°F</span>
        </div>
    </div>
</template>
<!-- ---- TEMPLATE ---- -->

<!-- ---- STYLE ---- -->
<style scoped>
.home {
  min-height: 50vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #1a1a2e;
}

.card {
  background-color: #16213e;
  padding: 50px 80px;
  border-radius: 24px;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.title {
  font-size: 28px;
  font-weight: bold;
  color: #f5a623;
  letter-spacing: 2px;
  text-transform: uppercase;
  text-align: center;
}

input {
  padding: 12px 20px;
  border-radius: 10px;
  border: 2px solid #f5a623;
  background: #1a1a2e;
  color: #e0e0e0;
  font-size: 18px;
  outline: none;
  text-align: center;
  width: 100%;
  transition: border-color 0.2s;
}

input:focus {
  border-color: #4fc3f7;
}

input::placeholder {
  color: #555;
}

.resposta {
  font-size: 20px;
  font-weight: 600;
  color: #4fc3f7;
  text-align: center;
  background-color: rgba(79, 195, 247, 0.06);
  padding: 14px 24px;
  border-radius: 10px;
  width: 100%;
}
</style>
<!-- ---- STYLE ---- -->