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
          <svg width="30" height="30" xmlns="http://www.w3.org/2000/svg" id="dropdown-button">
            <use href="/images.svg#icon" />
          </svg>
        </span>

        <svg width="30" height="30" xmlns="http://www.w3.org/2000/svg" id="settings-button">
          <use href="/images.svg#settings-gear" />
        </svg>
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

#dropdown-button {
  --dropdown-color: var(--select);
  transition-duration: 0.2s;
  scale: 0.3;
}

#dropdown-button:hover {
  --dropdown-color: var(--menu-hover);
  scale: 0.4;
}

#settings-button {
  --settings-color: var(--select);
  --bg-color: var(--bg);
  transition-duration: 0.2s;
}

#settings-button:hover {
  --settings-color: var(--menu-hover);
  scale: 1.15;
}

</style>
