<template>
 
  <book-item :book="book" />
</template>

<script>
import BookItem from './components/BookItem.vue'

export default {
  name: 'App',
  components: {
    BookItem
  },

  setup(){

    const book = {
      title:'The Cherry Orchard',
      author:'Anton Chekhov'
    }

    return {book}

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
