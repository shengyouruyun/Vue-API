<template>
  <div>
    <book-list :books="state.filteredBooks" />

    <book-search @search-by="filterBooks" />

    <BookDetails />
  </div>
</template>

<script>
import BookList from "./components/BookList.vue";
import BookSearch from "./components/BookSearch";
import BookDetails from "./components/BookDetails";
import { reactive } from "vue";

const books = [
  {
    id: 1,
    title: "The Cherry Orchard",
    author: "Anton Chekhov",
  },
  { id: 2, title: "Ivanov", author: "Tom Chekhov" },
];

function isInQuery(query) {
  return function (book) {
    return (
      (!query.title ||
        book.title.toLowerCase().includes(query.title.toLowerCase())) &&
      (!query.author ||
        book.author.toLowerCase().includes(query.author.toLowerCase()))
    );
  };
}

export default {
  name: "App",
  components: {
    BookList,
    BookSearch,
    BookDetails,
  },

  setup() {
    const state = reactive({
      filteredBooks: books,
    });

    function filterBooks(query) {
      state.filteredBooks = books.filter(isInQuery(query));
    }

    // function selectBook(id) {
    //   console.log(id);
    // }
    return {
      state,
      filterBooks,
    };
  },
};
</script>

<style>
</style>
