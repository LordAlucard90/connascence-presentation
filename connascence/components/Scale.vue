<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  l1: { default: false },
  l2: { default: false },
  l3: { default: false },
  l4: { default: false },
  l5: { default: false },
  l6: { default: false },
  l7: { default: false },
  l8: { default: false },
  l9: { default: false },
  l10: { default: false },
})

function getVisibilityClass(isVisible) {
  return isVisible ? 'visible' : 'hidden';
}

const isDynamicVisile = props.l6 ||props.l7 ||props.l8 ||props.l9 ||props.l10;
const isStaticVisile = props.l1 ||props.l2 ||props.l3 ||props.l4 ||props.l5;

const dynamicTypes = ref([
        { id: 10, name: 'Menual Task', isVisible: props.l10 },
        { id: 9, name: 'Identity', isVisible: props.l9  },
        { id: 8, name: 'Value',  isVisible: props.l8  },
        { id: 7, name: 'Timing',  isVisible: props.l7  },
        { id: 6, name: 'Execution Order',  isVisible: props.l6  },
      ])

const staticTypes = ref([
        { id: 5, name: 'Position', isVisible: props.l5 },
        { id: 4, name: 'Algorithm', isVisible: props.l4 },
        { id: 3, name: 'Meaning', isVisible: props.l3 },
        { id: 2, name: 'Type', isVisible: props.l2 },
        { id: 1, name: 'Name', isVisible: props.l1 },
      ])

</script>

<template>
  <div class="strength-scale">
    <span
      :class="getVisibilityClass(isDynamicVisile)" 
    >Dynamic:</span>
    <div
      v-for="(type, index) in dynamicTypes"
      :key="index"
      :class="['level', 'level-' + type.id, getVisibilityClass(type.isVisible)]"
      :style="{ '--index': index }"
    >
      <span>{{ type.name }}</span>
    </div>
    <span
      :class="getVisibilityClass(isStaticVisile)" 
    >Static:</span>
    <div
      v-for="(type, index) in staticTypes"
      :key="index"
      :class="['level', 'level-' + type.id, getVisibilityClass(type.isVisible)]"
      :style="{ '--index': index }"
    >
      <span>{{ type.name }}</span>
    </div>
  </div>
</template>

<style scoped>
.strength-scale {
  display: flex;
  flex-direction: column;
  flex: 1;
  gap: 8px;
  max-width: 600px;
}

.strength-scale .level {
  display: flex;
  align-items: center;
  position: relative;
  font-size: 16px;
  font-weight: bold;
  color: white;
  padding-left: 16px;
  height: 28px;
  clip-path: polygon(0 0, calc(100% - 20px) 0, 100% 50%, calc(100% - 20px) 100%, 0 100%);
}

.strength-scale .hidden {
  opacity: 0;
}

.level-10 {
  background-color: #FF0000;
  width: 300px;
  animation-delay: calc(var(--index) * 10s);
}

.level-9 {
  background-color: #FF4500;
  width: 280px;
  animation-delay: calc(var(--index) * 9s);
}

.level-8 {
  background-color: #FF6F00;
  width: 260px;
  animation-delay: calc(var(--index) * 8s);
}

.level-7 {
  background-color: #FFA500;
  width: 240px;
  animation-delay: calc(var(--index) * 7s);
}

.level-6 {
  background-color: #FFD966;
  width: 220px;
  animation-delay: calc(var(--index) * 6s);
}

.level-5 {
  background-color: #B6D758;
  width: 200px;
  animation-delay: calc(var(--index) * 5s);
}

.level-4 {
  background-color: #69B34C;
  width: 180px;
  animation-delay: calc(var(--index) * 4s);
}

.level-3 {
  background-color: #4CAF50;
  width: 160px;
  animation-delay: calc(var(--index) * 3s);
}

.level-2 {
  background-color: #3A9D23;
  width: 140px;
  animation-delay: calc(var(--index) * 2s);
}

.level-1 {
  background-color: #2E7D1A;
  width: 120px;
  animation-delay: calc(var(--index) * 1s);
}
</style>

