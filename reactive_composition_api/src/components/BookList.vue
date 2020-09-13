<template>

<div>
<BookItem v-for="book in books" :key="book.id" :book="book" />
</div>


</template>

<script>

import BookItem from './BookItem'
export default {
    props:{
        books:Array
    },

    components:{BookItem}


};
</script>

<style>
</style>