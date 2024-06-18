<template lang="">
  <div class="about">
    <h1>This is an about page</h1>
    <h1>counter -> <span>{{counter}}</span></h1>
    <button @click="increment()">Increment</button>
    <br>
    <br>
    <button @click="decrement()">Decrement</button>
    <br>
    <br>
    <button @click="Incrementx2()">Double Increment</button>
    <br>
    <br>
    <a href="https://www.youtube.com/watch?v=L1fGuPkNGUk" target="_blank"><img id='img' :src='imgUrl' alt='Click me' title='Click me' target></a>
    <h1 v-if="check">This is true</h1>
    <h1 v-else>This is false</h1>
    <button @click="checking()">Change State</button>
    <h1 v-show='check'>This is contains the v-show</h1>
    <ul>
      <li v-for='sport,index in sports' :key ="index">
        {{sport}}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data(){
    return{
      counter: 0,
      imgUrl: 'https://itz-marcus.github.io/Project-imagesV2/Board.png',
      check:true,
      sports:['soccer','netball','volleyball']
    }
  },
  methods: {
    increment(){
      this.counter++
    },
    decrement(){
      this.counter--
    },
    Incrementx2(){
      this.counter = this.counter+2
      
    },
    checking(){
      if (this.check ==true) {
        this.check = !true
      } else {
        this.check = true
      }
    }

  },
}
</script>
<style scoped>
  h1{
    background-image: linear-gradient(to bottom right, rgb(0, 255, 200), rgb(227, 27, 150));
  }
  #img{
    object-fit: contain;
    width: 19vw;
    transition: 0.3s;
  }
  #img:hover{
    width: 21vw;
    cursor: pointer;

  }
</style>
