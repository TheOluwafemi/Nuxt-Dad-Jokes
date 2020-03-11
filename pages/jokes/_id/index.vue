<template>
  <div>
    <nuxt-link class="back" to="/jokes">Back to Jokes</nuxt-link>
    <br />
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
    <hr />
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      joke: ''
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      )
      this.joke = res.data.joke
    } catch (err) {
      console.error(err)
    }
  }
}
</script>

<style scoped>
.back {
  margin-bottom: 2rem;
  background: darkgray;
  color: white;
  padding: 0.5rem;
}

.joke {
  margin-top: 2rem;
}

.joke p {
  line-height: 2;
  background: #fee;
  padding: 1rem;
  margin: 1rem 0;
  cursor: pointer;
  color: #666;
}
</style>
