<script setup lang="ts">
import { ref } from 'vue'
import Avatar from './components/Avatar.vue'

const initials = ref('HS')
</script>

<template>
  <div class="app">
    <div id="sidebar">
      <div id="account">
        <span>
          <Avatar :initials="initials" />
          <svg height="30" width="30" xmlns="http://www.w3.org/2000/svg">
            <polygon points="28,7.5 2,7.5 15,30" />
          </svg>
        </span>
      </div>
    </div>
  </div>
</template>

<style scoped>
#sidebar {
  width: 200px;
  height: 100vh;
  background-color: var(--menu1);
  border-right: 1px solid var(--outline);
}

#account {
  padding: 0.75rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid var(--outline);
}

#account>span {
  display: flex;
  align-items: center;
}

#account>span>svg {
  fill: var(--select);
  transition: fill 0.2s ease;
  scale: 0.5;
}

#account>span>svg:hover {
  fill: var(--menu-hover);
}
</style>
