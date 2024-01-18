<script>
    import BookForm from '../components/BookForm.vue';

    let array = []
    let id = 1 

    export default
    {
        name:"AddBookPage",
        components: {
            BookForm
        },
        methods: {
            add(book){

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
                    }
                    
                    const i = {
                        id:id,
                        title: book.title,
                        author: book.author,
                        page: book.page
                    };

                    
                    array.push(i);
                    console.log(array);
                    id++
                
                    book.title = ''
                    book.author = ''
                    book.page = ''

                }
                else {
                    alert("At least one argument is missing");
                }

                

            }

        }

    }
    export {array};

</script>

<template>
    <br><br><br>
    <h1 class="title">Add a book</h1>
    <br><br><br>
    <BookForm text="Add" :fonction=add />
</template>

<style></style>