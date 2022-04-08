<template>
  <div class="hello">
     Welcome
     <h2>Refs</h2>
     <p>{{vicOne.name}} - {{vicOne.age}}</p>
     <button @click="upDateVicOne">update vic one</button>
     <h2>Reactive</h2>
     <p>{{vicTwo.name}} - {{vicTwo.age}}</p>
     <button @click="upDateVicTwo">update vic two</button>
  </div>
</template>

<script>

import { ref, reactive } from 'vue'

export default {
  name: 'HelloWorld',
   

  setup(){
     const vicOne = ref({ name:'Omoefe', age:30})
     const vicTwo = reactive({name:'Joseph',age:32})

    const upDateVicOne = () =>{
      vicOne.value.age = 28
    }

    const upDateVicTwo = () =>{
      vicTwo.age = 28
    }

    return {vicOne,vicTwo,upDateVicOne,upDateVicTwo}
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
