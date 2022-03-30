<template>
  <div class="hello">
     Welcome
     <p ref="p">My name is {{name}} and my age is {{age}}</p>
     <button @click="handleClick">click me</button>
  </div>
</template>

<script>

import { ref } from 'vue'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  setup(){
    console.log("setup")

    const p = ref(null)

    let name = 'Omoefe'
    let age = 29

    const handleClick = () =>{
      console.log(p, p.value)
      p.value.classList.add('lagos')
      p.value.textContent = 'Hello, World'
    }

    return {name, age, handleClick, p}
  }
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
