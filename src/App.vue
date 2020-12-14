<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
     <h1>{{ title }}</h1>
   <ul>

     <li v-bind:key="book.title" v-for="book in books">
      Title: <b>{{ book.title }}</b> By: <b>{{ book.author }}</b>
     </li>
   </ul>
    <BookForm @addBook='appendBook' />
  </div>
</template>

<script>
import BookForm from './components/BookForm.vue';

export default {
  name: 'App',
  components: {
    BookForm
  },
  
   data() {
    return {
      title: 'All Books',
       books: [
                {title: 'Self-Reliance', author:'Ralph Waldo Emerson'},
                {title: 'American Gods', author:'Niel Gaiman'},
                {title: 'Amusing Ourselves to Death', author:'Niel Postman'},
                {title: 'The Chronicles of Simplified coding:', author:'Samuel Damilola'},
                {title: 'Coding Made Simple', author:'Samfrexz'},
            ]
    }
  },
   methods:{
        appendBook(bookTitle, bookAuthor){
            this.books.push({title: bookTitle, author: bookAuthor})
        }
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
ul {
   list-style-type: none;
 }
 
</style>
