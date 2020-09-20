<template>
<div>
  <book-list :books="books" @select="selectBook"/>

  <book-search @search-by="filterBooks" />

  <BookDetails/>

</div>
</template>

<script>
import BookList from "./components/BookList.vue";
import BookSearch from "./components/BookSearch";
import BookDetails from './componentss/BookDetails'

export default {
  name: "App",
  components: {
    BookList,BookSearch, BookDetails
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

    function selectBook(id){
      console.log(id)
    }
    return {
      books,
      filterBooks,
      selectBook
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
