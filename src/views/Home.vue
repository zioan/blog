<template>
  <div class="home">
    <h1>home</h1>
    <input type="text" v-model="search">
    <p>search term - {{search}}</p>
    <div v-for="name in names" :key="name">
      <p>{{name}}</p>
    </div>
    <h2>Sorted names</h2>
    <div v-for="name in matchingNames" :key="name">
      <p>{{name}}</p>
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref(['ioan', 'zaharia', 'john', 'doe', 'will', 'smith'])

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })
    
    return {names, search, matchingNames}
  }
}
</script>
