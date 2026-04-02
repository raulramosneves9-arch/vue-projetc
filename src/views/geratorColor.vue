<!-- ---- SCRIPT ---- -->
<script setup>

// ---- IMPORTS ----
import { ref, reactive } from 'vue';

// ---- DATA ----
const backgroundNames = reactive(["#e94560", "#4ecca3", "#f5a623", "#667eea", "#a855f7"])
const valorBackground = ref(0)

// ---- FUNCTIONS ----
function changeBakcground() {
    if (valorBackground.value < backgroundNames.length - 1) {
        valorBackground.value++
    } else {
        valorBackground.value = 0
    }
}

</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- TEMPLATE ---- -->
<template>
    <div class="card" :style="{ backgroundColor: backgroundNames[valorBackground] }">
        <button class="btn" @click="changeBakcground">SE CLICAR MUDA O BACKGROUND</button>
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
  padding: 60px 80px;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  transition: background 0.5s ease;
}

.btn {
  font-size: 16px;
  padding: 14px 28px;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  font-weight: bold;
  background: rgba(255, 255, 255, 0.1);
  color: #fff;
  letter-spacing: 1px;
  transition: transform 0.1s, box-shadow 0.2s;
  backdrop-filter: blur(4px);
}

.btn:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 20px rgba(255, 255, 255, 0.15);
}
</style>
<!-- ---- STYLE ---- -->