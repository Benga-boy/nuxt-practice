<template>
  <div>
    <h1>About this App</h1>
    <p>This was created by Benga to have a practice with Nuxt</p>
  </div>
</template>

<script>
export default {
  head() {
    return{
      title: 'About My App',
      meta: [{
        hid: 'description',
        name: 'description',
        content: 'Best way to learn new things'
      }]
    }
  }
}
</script>

<style>

</style>