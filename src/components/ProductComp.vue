<template >
    <div :style="{
        backgroundImage: `url(${cover})`,
        backgroundSize:`cover`,
        filter:`blur(4px)`
    }">
    </div>
        <!-- <h1>Products ↓</h1>
        {{theBooks.title}}
        <br>
        <img :src="theBooks.cover">
        <br>
        {{theBooks.author}}
        <br>
        {{theBooks.year}}
        <br>
        {{theBooks.genre}}
        <br>
        {{theBooks.pages}}
        <br>
        {{theBooks.publisher}}
        <br>
        {{theBooks.isbn}}
        -->
        <div>
          <slot name="heading"></slot>
        <slot name="author"></slot>
        <slot name="page"></slot>
        <slot></slot>   
        </div>
       
    </template>
<script>

export default {
    // props:['theBooks']
    props:["cover"]
}
</script>
<style>

    div{
        width: 300px;
        height: 400px;
        position: absolute;
        border-radius: 10%;
    }
    h1,h4{
        color: white;
        text-shadow: 3px 3px black;
    }
    img{
        object-fit: contain;
        height: 40vh;
    }
</style>