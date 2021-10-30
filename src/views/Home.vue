<template>
  <div class="home">
    <h1>home</h1>
    <input type="text" v-model="search">
    <div v-for="name in matchingNames" :key="name">
      <p>{{name}}</p>
    </div>
    <button @click="handleClick">stop watching</button>
  </div>
</template>

<script>
import { ref, computed, watch, watchEffect } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref(['ioan', 'zaharia', 'john', 'doe', 'will', 'smith'])

// run every time the value change but not until value change
    // watch(search, () => {
    //   console.log("watch function ran")
    // })
   const stopWatch = watch(search, () => {
      console.log("watch function ran")
    })

// run every time the value change AND on app first render
    // watchEffect(() => {
    //   console.log("watchEffect function ran", search.value)
    // })
   const stopEffect = watchEffect(() => {
      console.log("watchEffect function ran", search.value)
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }
    
    return {names, search, matchingNames, handleClick}
  }
}
</script>
