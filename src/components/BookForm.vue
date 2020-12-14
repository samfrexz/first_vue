<template>
    <div>
        <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)">
            <input  v-model="bookTitle" type="text" name="bookTitle" placeholder="Enter your book title">
            &nbsp;<input v-model="bookAuthor" type="text" name="bookAuthor" placeholder="Enter your book author">
           &nbsp; <input type="submit" value="Add Book">
        </form>
    </div>
</template>

<script>
export default {
    name: 'BookForm',
    props: ['books'],
    data() {
        return {
            bookTitle: '',
            bookAuthor: '',
        }
    },
     methods:{
        bookSubmit(bookTitle, bookAuthor){
            this.$emit('addBook', bookTitle, bookAuthor)
        }
    }
    
}
</script>

<style scoped>
input[type=submit] {
    padding: 8px 15px;
    background: black;
    color: white;
    border: none;
    cursor: pointer;
}
input[type=text] {
    padding: 7px 21px;

}
</style>