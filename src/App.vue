<script setup>
import ToggleIcon from './components/ToggleIcon.vue'
const itemId = 'MyToggle'

function handleToggle(active, id) {
  alert('the component with the ID: ' + id + ' was toggled to ' + active)
}
</script>

<template>
  <ToggleIcon @activeToggled="handleToggle" :itemId="itemId">
    <template #iconActive><font-awesome-icon icon="fa-eye" /></template>
    <template #iconInactive><font-awesome-icon icon="fa-eye-slash" /></template>
  </ToggleIcon>
</template>

<style scoped>
</style>
