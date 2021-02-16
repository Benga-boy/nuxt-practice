<template>
  <div>
    <h2>Welcome to my Posts App</h2>
  </div>
</template>

<script>
export default {
    head() {
    return{
      title: 'Posts Homepage',
      meta: [{
        hid: 'description',
        name: 'description',
        content: 'Check out some of the latest posts here'
      }]
    }
  }
}
</script>

<style>
</style>
