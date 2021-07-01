<template>
  <button
    :class="{'dark-mode': settings.theme === 'dark'}"
    @click="toggleMode"
  >
  Switch to {{ oppositeTheme }} mode
  </button>
</template>

<script>
import {inject, computed} from 'vue'
export default {
  setup() {
    const settings = inject('settings') // Second argument here is optional - default value if not available
    const oppositeTheme = computed(() => 
      settings.theme === 'dark' ? 'light' : 'dark'
    )
    const toggleMode = () => {
      settings.theme = oppositeTheme.value
    }

    return {settings, oppositeTheme, toggleMode}
  }
}
</script>

<style scoped>
.dark-mode {
  color: white;
  background-color: black;
}
</style>