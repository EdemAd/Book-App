<template>
    <header>
        <div name="navbar">
            <div>
                <img src="../assets/img/book.png" alt="logo">
            </div>
            <ul>
                <li>
                    <RouterLink to="/" class="link">Home</RouterLink>
                </li>
                <li>
                    <RouterLink to="/books/add" class="link">Add</RouterLink>
                </li>
            </ul>

        </div>
    </header>
</template>

<style>
    header {
        background-color: gray;
        width: 100%;
        height: 150px;
    }
    img {
        width: 75px;
        height: 75px;
        margin-bottom: 40px;
    }
    div {
        text-align: center;
    }
    li {
        list-style-type: none;
        display: inline;
        width: 50px;
        padding-left: 50px;
        padding-right: 50px;
        
    }
</style>