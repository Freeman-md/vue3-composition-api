<template>
  <div class="card">
    Component A
    <button @click.prevent="toggle = !toggle">Toggle</button>
    <teleport to='#endofbody' v-if="toggle">
      <p>Text from Component A</p>
    </teleport>
    <button @click.prevent="toggle2 = !toggle2">Toggle2</button>
    <teleport to='#endofbody' v-if="toggle2">
      <p>Another Text from Component A</p>
    </teleport>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  setup() {
    return {toggle: ref(false), toggle2: ref(false)}
  }
}
</script>