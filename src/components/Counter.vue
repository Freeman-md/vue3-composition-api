<template>
  <div>
    <button @click="increment">Counter</button>
    <div>{{counter}}</div>
    <div>{{arrayOfEmojis}}</div>
  </div>
</template>

<script>
import { onMounted, ref, watch, computed } from 'vue'
export default {
  props: {
    emoji: {type: String, default: '&#128169;'}
  }, 
  setup(props) { // called before the component is created and after the properties of the component are passed in.

    console.log(props.emoji)

    onMounted(() => {
      console.log('Counter component has been mounted')
    })

    const counter = ref(0)
    const increment = () => counter.value++

    watch(counter, current => {
      if (current === 5) console.log('You have clicked five times')
    })

    const arrayOfEmojis = computed(() => 
      Array.from(new Array(counter.value), () => props.emoji).join(' ')
    )

    return {increment, counter, arrayOfEmojis}

  }
}
</script>

<style>

</style>