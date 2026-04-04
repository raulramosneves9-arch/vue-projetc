<!-- ---- SCRIPT ---- -->
<script setup>

// ---- IMPORTS ----
import { reactive, watch, onMounted, onUpdated, onUnmounted } from 'vue'

// ---- DATA ----
const counterData = reactive({
    count: 0
})

// ---- FUNCTIONS ----

function incrementar(amount) {
    counterData.count += amount
}

function decrementar(amount) {
    counterData.count -= amount
}

function dobrar() {
    counterData.count = counterData.count * 2
}

function dividir() {
    counterData.count = counterData.count / 2
}

watch(() => counterData.count, (newCount) => {
    if (newCount >= 20) {
        console.log("WOW CONSEGUIU ATINGIR 20!!!")
    }
})

onMounted(() => {
    console.log("Contador montado com sucesso!")
})

onUpdated(() => {
    console.log("Contador atualizado. Valor atual: " + counterData.count)
})

onUnmounted(() => {
    console.log("Contador desmontado.")
})
</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- TEMPLATE ---- -->
<template>
    <div class="home">
        <div>
            <span>Contador: {{ counterData.count }}</span>
            <button class="btn" @click="incrementar(1)">+1</button>
            <button class="btn" @click="incrementar(2)">+2</button>
            <button class="btn" @click="decrementar(1)">-1</button>
            <button class="btn" @click="decrementar(2)">-2</button>
            <button class="btn" @click="dobrar">x2</button>
            <button class="btn" @click="dividir">/2</button>
        </div>
    </div>
</template>
<!-- ---- TEMPLATE ---- -->

<!-- ---- STYLE ---- -->
<style scoped>
.home {
    min-height: 70vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #1a1a2e;
}

.home div {
    background-color: #16213e;
    padding: 40px 60px;
    border-radius: 16px;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}

span {
    color: #e0e0e0;
    font-size: 48px;
    font-weight: bold;
}

.btn {
    font-size: 22px;
    margin: 6px;
    padding: 12px 28px;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    transition: transform 0.1s, opacity 0.2s;
    width: 100%;
}

.btn:hover {
    opacity: 0.85;
    transform: scale(1.05);
}

.btn:nth-child(1) {
    background-color: #4ecca3;
    color: #1a1a2e;
}

.btn:nth-child(2) {
    background-color: #4ecca3;
    color: #1a1a2e;
}

.btn:nth-child(3) {
    background-color: #e94560;
    color: #fff;
}

.btn:nth-child(4) {
    background-color: #e94560;
    color: #fff;
}

.btn:nth-child(5) {
    background-color: #f5a623;
    color: #1a1a2e;
}

.btn:nth-child(6) {
    background-color: #a855f7;
    color: #fff;
}
</style>
<!-- ---- STYLE ---- -->