<template>
  <section class="container">
    <div>
      <div>
        <img v-bind:src="results.primaryImageSmall">
      </div>
      <div>
        <span>
          {{ results.title }}
        </span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  async asyncData({ app }) {
    const id = Math.floor(Math.random() * 471581)
    const url = 'https://collectionapi.metmuseum.org/public/collection/v1/objects/'
    const data = await app.$axios.$get(url + id)
    console.log(id)
    console.log(data.primaryImageSmall)
    return { results: data }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
