<template>
  <v-container class="d-flex flex-column align-center justify-center fill-height">
    <h1 class="title">SEMÁFORO</h1>
    <SignalController />
  </v-container>
</template>

<script setup>
import SignalController from '~/components/SignalController.vue';
</script>

<style scoped>
.title {
  font-size: 28px;
  font-weight: bold;
  color: #333;
  text-align: center;
  margin-bottom: 24px;
}
</style>
