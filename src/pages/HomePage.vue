<script>

    
    import { array } from './AddBookPage.vue';
    import BookItem from '../components/BookItem.vue';
    

    export default {
    name: "HomePage",
    data() {
        return {
            books: array,
            search: ''
        };
    },
    computed: {
        filteredBooks() {
            return this.books.filter((i) => {
                return i.title.toLowerCase().includes(this.search.toLowerCase());
            });
        }
    },
    components: { BookItem }
    }
</script>


<template>
    <br><br><br>
    <input v-model="search" placeholder="Search..." class="searchbar">
    

    <br><br><br>
    
    <div v-for="i in filteredBooks" :key="i.id" class="box">
      <ul>
        <li class="list">
          <BookItem :book="i"/>
          <RouterLink :to="{ name: 'bookpage', params:{id: i.id}}" class="link"><p class="inblack">Show details</p></RouterLink>
        </li>
      </ul>
    </div>

    <div v-if="filteredBooks.length == 0 && search!==''">
        <p>No books found</p>
    </div>
</template>


<style>

    li {
        margin-top: 10px;
        text-align: center;
    }
</style>