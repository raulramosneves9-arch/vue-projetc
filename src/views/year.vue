<!-- ---- SCRIPT ---- -->
<script setup>

// ---- IMPORTS ----
import { ref, computed } from 'vue'

// ---- DATA ----
const anoNascimento = ref(null)
const newYear = 2026

// ---- COMPUTED ----
const idade = computed(() => {
    if (!anoNascimento.value) return '...'
    return newYear - anoNascimento.value
})

</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- TEMPLATE ---- -->
<template>
    <div class="home">
        <div>
            <span class="title">Contador de idade</span>
            <input v-model.number="anoNascimento" type="number" placeholder="Ano que você nasceu">
            <span class="resposta">Sua idade é: {{ idade }}</span>
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

.home div {
  background-color: #16213e;
  padding: 50px 80px;
  border-radius: 24px;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.title {
  font-size: 36px;
  font-weight: bold;
  color: #f5a623;
  letter-spacing: 2px;
  text-transform: uppercase;
}

.resposta {
  font-size: 20px;
  font-weight: 500;
  color: #4fc3f7;
  text-align: center;
  background-color: rgba(79, 195, 247, 0.06);
  padding: 14px 24px;
  border-radius: 10px;
  width: 100%;
  line-height: 1.8;
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
</style>
<!-- ---- STYLE ---- -->