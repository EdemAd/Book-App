<script>
    
    export default {
        name: "BookItem",
        
        props:{
            book:Object
        }
        
    }
</script>

<template>
    <div v-if="book" class="bookfont">
        <h3 class="title"><u> {{ book.title }} </u></h3>
        
        Author: {{ book.author }}
        <br>
        Number of pages: {{ book.page }}
        <br>
    </div>
</template>

<style>
    .align {
        text-align: center;
    }
</style>