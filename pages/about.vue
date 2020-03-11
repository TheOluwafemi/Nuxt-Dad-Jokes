<template>
  <div class="about">
    <h2>Dad Jokes</h2>

    <p>This app displays random Dad jokes</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'About the App',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place in the world for corny dad jokes'
        }
      ]
    }
  }
}
</script>

<style lang="css" scoped>
.about {
  text-align: center;
  margin: auto;
  padding: 3rem;
}
</style>
