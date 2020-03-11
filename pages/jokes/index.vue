<template>
  <div class="jokes">
    <SearchJoke @search-text="searchText" />
    <Joke
      v-for="joke in jokes"
      :id="joke.id"
      :key="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '../../components/joke'
import SearchJoke from '../../components/SearchJoke'

export default {
  components: {
    Joke,
    SearchJoke
  },
  data() {
    return {
      jokes: []
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
    } catch (err) {
      console.error(err)
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }
      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )
        this.jokes = res.data.results
      } catch (err) {
        console.error(err)
      }
    }
  },
  head() {
    return {
      title: 'Dad Jokes',
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

<style scoped>
.jokes {
  padding: 1.5rem;
}

p {
  line-height: 2;
  background: #fee;
  padding: 1rem;
  margin: 1rem 0;
  cursor: pointer;
}
</style>
