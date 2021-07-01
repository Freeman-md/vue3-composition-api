<template>
  <slot /> <!-- This will only render the components inside the HTML tags -->
</template>

<script>
import { provide, reactive, watch } from 'vue'
export default {
  setup() {
    const settings = reactive({
      theme: 'light' 
    })

    provide('settings', settings)

    watch(settings, settings => {
      console.log(
        `SettingsProvider: theme has been switched to ${settings.theme} mode.`
      )
    })
  }
}
</script>