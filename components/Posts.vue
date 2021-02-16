<template>
<nuxt-link :to="'posts/' + id">
  <div class="post">
    <h2>{{title}}</h2>
    <p>{{body}}</p>
  </div>
</nuxt-link>
</template>

<script>
export default {
  name: 'Post',
  props: ['title', 'body', 'id']
}
</script>

<style>
  .post  {
    border: 2px solid #000;
    margin: 1rem 0;
    text-align: center;
    max-width: 500px;
    padding: 1rem;
  }

  h2{
    margin-bottom: 1rem;
  }
</style>