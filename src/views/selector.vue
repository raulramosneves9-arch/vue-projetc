<!-- ---- SCRIPT ---- -->
<script setup>

// ---- IMPORTS ----
import { computed, reactive } from 'vue'

// ---- DATA ----
const counterData = reactive({
    count: 0
})

// ---- COMPUTED ----
const trueOrfalse = computed(() => {
    if (counterData.count % 2 === 0) {
        return 'Par'
    } else {
        return 'Impar'
    }
})

</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- TEMPLATE ---- -->
<template>
    <div class="home">
        <div>
            <span class="titulo">True or False</span>
            <span class="pergunta">É par?</span>
            <span class="pergunta">É impar?</span>
            <input v-model.number="counterData.count" type="number" placeholder="Digite um número">
            <span class="resposta">A resposta, do numero {{ counterData.count }}, é:
                <span class="resultado">{{ trueOrfalse }}</span>
            </span>
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

.titulo {
  font-size: 36px;
  font-weight: bold;
  color: #f5a623;
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 8px;
}

.pergunta {
  font-size: 20px;
  font-weight: 600;
  color: #e0e0e0;
  text-align: center;
  background-color: rgba(255, 255, 255, 0.04);
  padding: 10px 24px;
  border-radius: 10px;
  width: 100%;
  letter-spacing: 1px;
  font-style: italic;
}

.resposta {
  font-size: 18px;
  font-weight: 500;
  color: #c0c0c0;
  text-align: center;
  background-color: rgba(79, 195, 247, 0.06);
  padding: 14px 24px;
  border-radius: 10px;
  width: 100%;
  line-height: 1.8;
}

.resultado {
  font-size: 22px;
  font-weight: 700;
  color: #4fc3f7;
  background: none;
  padding: 0;
  margin-left: 6px;
}
</style>
<!-- ---- STYLE ---- -->