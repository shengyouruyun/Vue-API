<template>
<div>
  <book-list :books="books" />

  <book-search @search-by="filterBooks" />

</div>
</template>

<script>
import BookList from "./components/BookList.vue";
import BookSearch from "./components/BookSearch"

export default {
  name: "App",
  components: {
    BookList,BookSearch
  },

  setup() {
    const books = [
      {
        title: "The Cherry Orchard",
        author: "Anton Chekhov",
      },
      {
        title: "Ivanov",
        author: "Tom Chekhov",
      },
    ];

    function filterBooks(query){
      console.log(query)
    }
    return {
      books,
      filterBooks
    };
  },
};
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
