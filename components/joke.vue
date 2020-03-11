<template>
  <nuxt-link :to="'jokes/' + id">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id']
}
</script>

<style scoped>
.joke p {
  line-height: 2;
  background: #fee;
  padding: 1rem;
  margin: 1rem 0;
  cursor: pointer;
}
</style>
