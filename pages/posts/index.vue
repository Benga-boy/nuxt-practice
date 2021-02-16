<template>
  <div>
    <Post v-for="post in posts" :key="post.id" :id="post.id" :title="post.title" :body="post.body" />
  </div>
</template>

<script>
import axios from 'axios'
import Post from '../../components/Posts'

export default {
  components: {
    Post
  },
  data() {
    return {
      posts: []
    }
  },
  async created(){
    // * Fetch thee posts on mount
    try {
      const res = await axios.get('https://jsonplaceholder.typicode.com/posts')
      this.posts = res.data.slice(0, 9)
    } catch (err) {
      console.log(err)
    }
    console.log('Posts: ', this.posts)
  },
    head() {
    return{
      title: 'Latest Posts',
      meta: [{
        hid: 'description',
        name: 'description',
        content: 'Check out the latest posts'
      }]
    }
  }
}
</script>

<style>

</style>