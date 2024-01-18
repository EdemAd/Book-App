<script>
    export default{
        name:"BookForm",
        data(){
            return{
                book:{
                    title:'',
                    author:'',
                    page:'',
                }
            }
        },
        props:{
            fonction:Function,
            text:String,
        }
    }

</script>

<template>
    <div name="form" class="form">
        <form action="">
            <label>Title</label>
            <input type="text" v-model="book.title">
            <label>Author</label>
            <input type="text" v-model="book.author">
            <label>Page count</label>
            <input type="number" min="1" v-model="book.page">
            <br><br>
            <button type="button" @click="fonction(book)" class="btn">{{ text }}</button>
        </form>

    </div>
</template>

<style>
    form {
        align-items: center;
    }

    input {
        margin-left: 5px;
    }
    label {
        margin-left: 15px;
    }
    
</style>