<script lang="ts" setup>
import { computed } from 'vue'

const props = defineProps({
  initials: {
    type: String,
    required: true,
    default: '??'
  }
})

const avatarColor = computed(() => {
  const clean = props.initials.toUpperCase()
    let score = 0
  for (let i = 0; i < clean.length; i++) {
    score += clean.charCodeAt(i)
  }
  const hue = score % 360 // stay in hsl hue color space
  return `hsl(${hue}, 60%, 45%)`
})
</script>

<template>
  <div id="initials" :style="{ backgroundColor: avatarColor }">
    <span>{{ initials.toUpperCase() }}</span>
  </div>
</template>


<style scoped>
div {
  user-select: none;
}

#initials {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: bold;
  font-family: sans-serif;
  font-size: 14px;
}
</style>