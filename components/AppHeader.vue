<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/jokes">Jokes</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-bottom: 1rem;
  margin-bottom: 1rem;
  border-bottom: 1px dotted #ccc;
}

.title {
  font-size: 3rem;
  color: #526488;
}

header ul {
  display: flex;
  list-style-type: none;
}

header a {
  display: inline-block;
  background: #333;
  color: #ffffff;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
}
</style>
