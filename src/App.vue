<template>
<div id="app">
    <Search />
    <div class="container mx-auto">
      <div class='flex flex-wrap'>
          <PhotoCard v-for='book in booklist' :key='book.id' v-bind:title="book.title" v-bind:url="book.thumbnailUrl" />
      </div>
    </div>
  </div>
</template>

<script>
import PhotoData from './dummy/data.json'
import Search from './components/Search'
import PhotoCard from './components/PhotoCard'

export default {
  name: 'App',
  components: {
    PhotoCard,
    Search
  },
  data(){
    return{
      booklist: PhotoData,
    };
  },
  created(){
    console.log("list", this.booklist)
  },
  computed: {
    filteredList() {
      return this.booklist.filter(book => {
        return book.title.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  }
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
