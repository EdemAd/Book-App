
<script>
    import BookItem from '../components/BookItem.vue';
    import BookForm from '../components/BookForm.vue';
    import {array} from '../pages/AddBookPage.vue';
    

    export default
    {
        name:"AddBookPage",
        data(){
            return{
                showForm: false,
                currentBook: array.find(book => book.id === Number(this.$route.params.id)) 

            }
        },
        components: {
            BookForm,
            BookItem
        },
        methods: {
            modify(book){

                if (book.title && book.author && book.page >= 1 ) {

                    for (let index = 0; index < array.length; index++) {
                        if((array[index].title ===  book.title)&&(array[index].author === book.author))
                        {

                            alert("This book is already in your list ");
                            book.title = ''
                            book.author = ''
                            book.page = ''
                            return;
                        }
                        else if (array[index].id == this.$route.params.id)
                        {
                            const i = {
                            id: Number(this.$route.params.id),
                            title: book.title,
                            author: book.author,
                            page: book.page
                            };

                            this.currentBook = i;
                            array[index] = i;

                        }
                    }
    
                    console.log(array);
                
                    book.title = ''
                    book.author = ''
                    book.page = ''

                }
                else {
                    alert("At least one argument is missing");
                }


            },

            deleteBook(){
                const index = array.findIndex(book => book.id == this.$route.params.id)

                if(index !== -1)
                {
                    array.splice(index,1)
                }
                console.log(array)
            
                alert("Your book has been delete !")
                
            }
        }

    }
</script>

<template>
    <br><br>
    <div class="box">
        <BookItem :book="currentBook" />
        <br><br>
    </div>
    <br>
    <button type="button" @click="showForm = !showForm" class="btn">modify</button>
    <br>
    <br>
    <br>
    <div v-if="showForm">
        <BookForm :fonction=modify text="save"/>
        <RouterLink to="/">
            <button type="button" @click="deleteBook" class="btn">delete</button>
        </RouterLink>
    </div>

</template>



