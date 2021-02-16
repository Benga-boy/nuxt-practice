<template>
  <div>
    <SearchPosts v-on:search-text="searchText" />
    <Post v-for="post in posts" :key="post.id" :id="post.id" :title="post.title" :body="post.body" />
  </div>
</template>

<script>
import axios from 'axios'
import Post from '../../components/Posts'
import SearchPosts from '../../components/SearchPosts'

export default {
  components: {
    Post,
    SearchPosts
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
  methods: {
    searchText(text) {
      // Filter posts by keywords in the title
      if (this.posts.length > 0) {
        this.posts = this.posts.filter(post => post.title.includes(text))
      }
    }
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