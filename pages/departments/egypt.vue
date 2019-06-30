<template>
  <section class="container">
    <div>
      <div v-if="results.primaryImageSmall !== ''">
        <img v-bind:src="results.primaryImageSmall">
      </div>
      <div v-else class="no-picture">
        No Picture
      </div>
      <div>
        <span>
          {{ results.title }}
        </span>
      </div>
      <div>
        <span>
          {{ results.artistDisplayName }}
        </span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  async asyncData({ app }) {
    const departmentUrl = 'https://collectionapi.metmuseum.org/public/collection/v1/objects?departmentIds=10'
    const objectIdData = await app.$axios.$get(departmentUrl)
    const objectIds = objectIdData.objectIDs
    const index = Math.floor(Math.random() * objectIds.length)
    const objectId = objectIds[index]
    const url = 'https://collectionapi.metmuseum.org/public/collection/v1/objects/'
    const data = await app.$axios.$get(url + objectId)
    console.log('pic url:', data.primaryImageSmall)
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
