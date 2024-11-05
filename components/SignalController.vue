<template>
  <v-row class="signal-controller">
    <div class="signal-body">
      <SignalLight color="red" :isActive="currentLight === 'red'" />
      <SignalLight color="yellow" :isActive="currentLight === 'yellow'" />
      <SignalLight color="green" :isActive="currentLight === 'green'" />
    </div>

    <v-col class="button-column">
      <v-btn @click="changeLight('red')" class="red-button">Rojo</v-btn>
      <v-btn @click="changeLight('yellow')" class="yellow-button">Amarillo</v-btn>
      <v-btn @click="changeLight('green')" class="green-button">Verde</v-btn>
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

.light {
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5); 
}

.light.active {
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.8); 
}


.button-column {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.red-button {
  background-color: #e53935;
  color: white;
}

.yellow-button {
  background-color: #ffeb3b;
  color: black;
}

.green-button {
  background-color: #4caf50;
  color: white;
}
</style>
