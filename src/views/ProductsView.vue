<template lang="">
    <div>
        <h1>This is the Products Page</h1>
    </div>
    
    <div id='flexing'>
                                   <!-- Table form -->
            <!-- <table>
                <thead>
                    <tr>
                        <th>Title</th>
                        <th>Author</th>
                        <th>Year</th>
                        <th>Genre</th>
                        <th>Pages</th>
                        <th>Publisher</th>
                        <th>ISBN</th>
                    </tr>
                </thead>
                <tbody v-for='({title,author,year,genre,pages,publisher,isbn},index ) in books' :key="index">
                <tr>
                    <td>
                        {{title}}  
                    </td>
                    <td>
                        {{author}}  
                    </td>
                    <td>
                        {{year}}  
                    </td>
                    <td>
                        {{genre}}  
                    </td>
                    <td>
                        {{pages}}  
                    </td>
                    <td>
                        {{publisher}}  
                    </td>
                    <td>
                        {{isbn}}  
                    </td>
                </tr>
                    
                </tbody>
            </table> -->

                                    <!--Slot Card form (mine) -->

        <!-- <div id='flexing'>
            <slots-comp v-for='({title,author,year,genre,pages,publisher,isbn,cover},index ) in books' :key="index">
                <template #slotTitle>
                    <h3><u>{{title}}</u></h3>
                </template>
                <template #default>
                    <img :src=cover>
                    <p>Author: {{author}}</p>
                    <p>Publisher: {{publisher}}</p>
                    <p>Year: {{year}} Pages: {{pages}}</p>
                    <p>Genre: {{genre}}</p>
                    <p>ISBN: {{isbn}}</p>            
                </template>
            </slots-comp>
        </div>
         -->
                                     <!-- thing -->
        <section v-for = "book in books" :key="book">
            <!-- <product-comp :the-books="book"/> -->
            <!-- Cards -->
            <product-comp :cover="book.cover">
                <template #heading>
                    <h1>{{book.title}}</h1>
                </template>
                <template #author>
                    <h4>{{book.author}}</h4>
                </template>
                <template #pages>
                    <h4>{{book.pages}}</h4>
                </template>
                <template #default>
                    <h4>{{book.publisher}}</h4>
                </template>
            </product-comp>
        </section>  
    </div>
</template>
<script>
/* eslint-disable */
import ProductComp from "@/components/ProductComp.vue";
// import SlotsComp from "../components/SlotsComp.vue";
export default {
    data(){
        return{
            books:[
            {title: "The Great Gatsby",    
            author: "F. Scott Fitzgerald",    
            year: 1925,    
            genre: "Literary Fiction",    
            pages: 180,   
            publisher: "Charles Scribner's Sons",    
            isbn: "978-0743273565", 
            cover:'https://i0.wp.com/americanwritersmuseum.org/wp-content/uploads/2018/02/CK-3.jpg?resize=267%2C400&ssl=1' 
            },  
            {title: "To Kill a Mockingbird",
            author: "Harper Lee",    
            year: 1960,    
            genre: "Southern Gothic",    
            pages: 281,    
            publisher: "J. B. Lippincott & Co.",    
            isbn: "978-0446310789",
            cover:'https://media.glamour.com/photos/56e1f3c462b398fa64cbd304/master/w_1600%2Cc_limit/entertainment-2016-02-18-main.jpg'  
            },  
            {title: "1984",    
            author: "George Orwell",   
            year: 1949,    
            genre: "Dystopian Fiction",    
            pages: 328,    
            publisher: "Secker & Warburg",    
            isbn: "978-0451524935",
            cover:'https://i0.wp.com/www.printmag.com/wp-content/uploads/2017/01/2a34d8_463ff497abfa4bca9b96d696e911746fmv2.jpeg?resize=500%2C769&quality=89&ssl=1'  
            },  
            {title: "Pride and Prejudice",    
            author: "Jane Austen",    
            year: 1813,    
            genre: "Romance",    
            pages: 279,    
            publisher: "Thomas Egerton",    
            isbn: "978-0141439513",
            cover:'https://cdn.kobo.com/book-images/08ba5a67-f48d-420e-be8e-6de7a73b7d85/1200/1200/False/pride-prejudice-13.jpg'  
            },  
            {title: "The Catcher in the Rye",    
            author: "J.D. Salinger",    
            year: 1951,    
            genre: "Coming-of-age Fiction",    
            pages: 214,    
            publisher: "Little, Brown and Company",    
            isbn: "978-0316769488",
            cover:'https://cdn.britannica.com/94/181394-050-2F76F7EE/Reproduction-cover-edition-The-Catcher-in-the.jpg'  
            }
            ]
        }
    },
    components:{
      ProductComp,
    //   SlotsComp
    }
}
</script>
<style scoped>
    section{
        border: 3px black solid;
        border-radius: 20px;
        width: 300px;
        height: auto;
    }
    table,th,tr,td{
        border: 2px solid black;
    }
    p{
        font-size: 2vh;
    }
    img{
        object-fit: contain;
        height: 40vh;
    }
    #flexing{
        display: grid;
        grid-template-columns: repeat(5, 1fr);
    }
</style>