<template>
  <div class="hello">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>search name - {{ search }}</p>
    <button @click="handleClick">Stop Watching</button>
    <div v-for="name in matchingName" :key="name">{{ name }}</div>

  </div>
</template>

<script>

import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'HelloWorld',
  
  setup(){
      const search = ref('')
      const names = ref(['Omoefe','Joseph','Ugboma','Melissa','Annabelle','Maureen'])
   
   const matchingName = computed(()=>{
     return names.value.filter((name) =>name.includes(search.value))
   })

  const stopWatch = watch(search, () => {
     console.log('watching for search')
   })

    const stopEffect = watchEffect(() => {
     console.log('watching Effects for search', search.value)
   })

    const handleClick = () =>{
      stopWatch()
      stopEffect()
    }

   return {names, search, matchingName, handleClick}
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
