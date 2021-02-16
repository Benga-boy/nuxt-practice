<template>
  <div>
    <header class="header">
      <h1 class="title">Latest Posts</h1>
      <ul>
        <li>
          <nuxt-link to="/">Home</nuxt-link>
          <nuxt-link to="/about">About</nuxt-link>
          <nuxt-link to="/posts">Posts</nuxt-link>
        </li>
        <li></li>
        <li></li>
      </ul>
    </header>
  </div>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px dotted #ccc;
  }
  .header .title {
    font-size: 3rem;
    color: aquamarine;
  }
  .header ul{
    display: flex;
    list-style: none;
  }

  .header a {
    display: inline-block;
    background: #331;
    color: #fff;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }
</style>