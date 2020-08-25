<template>
<div id="app">
    <div class="container mx-auto">
      <div class='flex flex-wrap'>
          <PhotoCard v-for='book in booklist' :key='book.id' v-bind:title="book.title" v-bind:url="book.thumbnailUrl" />
      </div>
    </div>
  </div>
</template>

<script>
import PhotoData from './dummy/data.json'

import PhotoCard from './components/PhotoCard'

export default {
  name: 'App',
  components: {
    PhotoCard
  },
  data(){
    return{
      booklist: PhotoData,
    };
  },
  created(){
    console.log("list", this.booklist)
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
