<template>
  <div class="book-item">
    <div>{{book.title}}</div>
    <div>{{book.author}}</div>
  </div>
</template>

<script>
export default {
  name: "BookItem",
  props: {
    book: Object,
  },
};
</script>

<style>
.book-item {
  display: flex;
}
.book-item > div {
  flex: 1;
}
</style>