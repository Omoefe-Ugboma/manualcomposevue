<template>
  <div class="post-lists">
      <div v-for="post in posts" :key="post.id">
        <SinglePost :post="post"/>
        <!-- <h3>{{ post.title}}</h3> -->
      </div>
  </div>      
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from 'vue'
import SinglePost from './SinglePost.vue'
export default{
    props: ['posts'],
    components: { SinglePost },
    setup(props) {
        onMounted(() =>console.log('component mounted',props.posts))
        onUnmounted(() =>console.log('component Unmounted',props.posts))
        onUpdated(() =>console.log('component updated',props.posts))
    }
    

}

</script>

<style>

</style>