<!-- ---- TEMPLATE ---- -->
<template>
    <div class="react">
        <div>
            <span>{{ appTitle }}</span>
            <hr>
            <button class="btn" @click="nameBack">Voltar</button>
            <span>Mude meu nome: {{ name }}</span>
            <button class="btn" @click="nameChange">Avançar</button>
            <hr>
            <span>Digite um nome da qual queira modificar:</span>
            <input v-model="counterData.title" type="text">
        </div>
    </div>
</template>
<!-- ---- TEMPLATE ---- -->

<!-- ---- SCRIPT ---- -->
<script setup>

// ---- IMPORTS ----
import { reactive, ref, computed } from 'vue'

// ---- DATA ----
const counterData = reactive ({
  title: computed({
  get: () => namesArray[valorArray.value],
  set: (val) => { namesArray[valorArray.value] = val }
  })
})
const appTitle = 'Merda (um titulo merda)'
const namesArray = reactive(['Raul', 'Rafa', 'Fernanda', 'Lucas', 'Mariana', 'Pedro', 'Juliana', 'Carlos', 'Beatriz', 'Thiago'])
const valorArray = ref(0)

// ---- COMPUTED ----
const name = computed(() => namesArray[valorArray.value])

// ---- FUNCTIONS ----
function nameChange() {
  if (valorArray.value < namesArray.length - 1) valorArray.value++
}

function nameBack() {
  if (valorArray.value > 0) valorArray.value--
}

</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- STYLE ---- -->
<style scoped>
.react {
  min-height: 70vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #1a1a2e;
}

.react div {
  background: #16213e;
  padding: 40px 60px;
  border-radius: 20px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

span {
  font-size: 24px;
  font-weight: 600;
  color: #e0e0e0;
  text-align: center;
}

span:first-child {
  font-size: 32px;
  color: #e0e0e0;
}

input {
  padding: 10px 20px;
  border-radius: 50px;
  border: 2px solid #667eea;
  background: #1a1a2e;
  color: #e0e0e0;
  font-size: 18px;
  outline: none;
  text-align: center;
  width: 100%;
}

input:focus {
  border-color: #a855f7;
}

.btn {
  font-size: 18px;
  padding: 12px 24px;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  font-weight: bold;
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: #fff;
  transition: transform 0.1s, box-shadow 0.2s;
  width: 100%;
}

.btn:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 15px rgba(102, 126, 234, 0.5);
}

hr {
  border: none;
  border-top: 2px solid #667eea;
  width: 100%;
  opacity: 0.4;
}
</style>
<!-- ---- STYLE ---- -->