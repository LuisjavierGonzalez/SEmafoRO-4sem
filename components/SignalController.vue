<template>
  <v-row class="signal-controller">
    <div class="signal-body">
      <SignalLight color="red" :isActive="currentLight === 'red'" />
      <SignalLight color="yellow" :isActive="currentLight === 'yellow'" />
      <SignalLight color="green" :isActive="currentLight === 'green'" />
    </div>

    <v-col class="button-column">
      <button @click="changeLight('red')" class="color-button red-button">Rojo</button>
      <button @click="changeLight('yellow')" class="color-button yellow-button">Amarillo</button>
      <button @click="changeLight('green')" class="color-button green-button">Verde</button>
    </v-col>
  </v-row>
</template>

<script setup>
import { ref } from 'vue';
import SignalLight from '~/components/SignalLight.vue';

const currentLight = ref('red');

function changeLight(color) {
  currentLight.value = color;
}
</script>

<style scoped>
.signal-controller {
  display: flex;
  align-items: center;
  gap: 24px;
  justify-content: center;
  padding-top: 20px;
}

.signal-body {
  width: 90px;
  background-color: #222;
  padding: 12px;
  border-radius: 12px; 
  display: flex;
  flex-direction: column;
  align-items: center;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.7); 
}

.button-column {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.color-button {
  padding: 10px 20px; 
  border: none;
  border-radius: 20px; 
  font-weight: bold;
  cursor: pointer;
  color: white;
  width: 80px;
  text-align: center;
  transition: transform 0.2s;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3); 
}

.color-button:hover {
  transform: scale(1.05); 
}

.red-button {
  background-color: #e53935; 
}

.yellow-button {
  background-color: #ffeb3b; 
  color: black; 
}

.green-button {
  background-color: #4caf50; 
}
</style>
