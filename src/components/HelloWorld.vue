<template>
  <div class="hello">
    <h1>Home</h1>
    
    <PostList :posts="posts"/>
  </div>
</template>

<script>

import  PostList  from '../components/PostList.vue'

import { ref } from 'vue'

export default {
  name: 'HelloWorld',
  components:{ PostList},
  setup(){
     const posts = ref([
       {title:"Lion King", body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sed velit accusamus voluptatem minus ipsam reiciendis vero recusandae odit laboriosam perspiciatis adipisci, necessitatibus doloribus, beatae blanditiis expedita placeat optio. Neque, earum? ', id:1 },
       {title:"Jungle King", body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sed velit accusamus voluptatem minus ipsam reiciendis vero recusandae odit laboriosam perspiciatis adipisci, necessitatibus doloribus, beatae blanditiis expedita placeat optio. Neque, earum? ', id:1 }

     ])

   return {posts}
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
