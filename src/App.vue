<template>
  <SettingsProvider>
    <ThemeButton />
  </SettingsProvider>
</template>

<script>
import SettingsProvider from './components/SettingsProvider.vue'
import ThemeButton from './components/ThemeButton.vue'

export default {
  components: {SettingsProvider, ThemeButton}
}
</script>