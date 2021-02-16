<template>
  <div v-if="post">
    <nuxt-link to="/posts">Back to posts</nuxt-link>
    <Post :title="post.title" :body="post.body" :id="post.id" />
  </div>
</template>

<script>
import Post from '../../../components/Posts'
import axios from 'axios'

export default {
  components: {
    Post
  },
  data() {
    return {
      post: {}
    } 
  },
  async created(){
    try {
      const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
      this.post = res.data
    } catch (err) {
      console.log(err)
    }
  }
}
</script>

<style>

</style>