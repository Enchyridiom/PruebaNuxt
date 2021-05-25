<template>
   <p v-if="$fetchState.pending">Fetching mountains...</p>
  <p v-else-if="$fetchState.error">An error occurred :(</p>
  <div v-else>
    <h1>Nuxt Mountains</h1>
    <ul>
      <li v-for="mountain of mountains" :key="mountain.Apupdate">{{ mountain.title  + ' ' + mountain.height}}</li>
    </ul>
    <button @click="$fetch">Refresh</button>

    <header-image :source="'/img1.jpg'" :demo="'graffiti'" :end="'Fin de la página'" />
  </div>
</template>

<script>
export default{
    data() {  //lugar de almacenamiento para guardar variables exteriores
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/mountains'
      ).then(res => res.json())
    }
  }
</script>

<style>
</style>