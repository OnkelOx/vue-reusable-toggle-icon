<template>
  <div v-if="$slots.iconActive && $slots.iconInactive" @click="toggleActive" class="toggleIcon">
    <slot v-if="active" name="iconActive"></slot>
    <div v-else class="disabled">
      <slot name="iconInactive"></slot>
    </div>
  </div>
  <button v-if="!$slots.iconActive || !$slots.iconInactive">test</button>
</template>

<script setup>
import { ref, defineEmits, getCurrentInstance } from 'vue'

const emit = defineEmits(['activeToggled'])
const props = defineProps({
  itemId: {
    Type: String,
    required: true
  }
})
const active = ref(true)

function toggleActive() {
  active.value = !active.value
  emit('activeToggled', active.value, props.itemId)
}
</script>

<style scoped>
.toggleIcon {
  position: relative;
  height: 1em;
}

.disabled * {
  color: #880000;
}
</style>