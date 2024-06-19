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
    <a href="https://www.youtube.com/watch?v=L1fGuPkNGUk" target="_blank"><img id='img' :src='imgUrl'  title='Click me' loading="lazy"></a>
    <h1 v-if="check">This is true</h1>
    <h1 v-else>This is false</h1>
    <button @click="checking()">Change State</button>
    <h1 :class='{hello:check}'>Conditional rendering</h1>
    <h1 v-show='check'>This is contains the v-show</h1>
    <br>
    <ul>

      <!-- <li v-for='sport,index in sports' :key ="index">
        {{sport}}
      </li> -->

      <li v-for='({message},index ) in objects' :key="index">
        {{message}}
      </li>

    </ul>
    <input placeholder='Type here' type="text" v-model='inputtxt' >
    <p v-once>{{ msg }}</p>
    <br>
    <br>
    <br>
    <span>'Your text:' {{inputtxt}}</span>
    <!-- one way data binding -->
    <h2>{{oneWayText}}</h2>
    <!-- two way data binding -->
    <h2>{{twoWayText}}</h2>
    <input type= 'text' placeholder='2.0' v-model="twoWayText">
  </div>
  <!-- <info-comp first-name='hehe' last-name=' hehehehe'/>
  <info-comp first-name='hehe1' />
  <info-comp :object-data='singleObject'/> -->
  <info-comp>
      hehe im am using slots
  </info-comp>

  <slots-comp>
    <template #slotTitle>
      Card Slot
    </template>
    <template #default>
      <img :src="imgUrl" id='img'>
    </template>
  </slots-comp>
  

</template>
<script>
import InfoComp from "../components/InfoComp.vue";
import SlotsComp from "../components/SlotsComp.vue";
export default {
  data(){
    return{
      counter: 0,
      imgUrl: 'https://itz-marcus.github.io/Project-imagesV2/Board.png',
      check:true,
      sports:['soccer','netball','volleyball'],
      msg:'Sup yall',
      inputtxt: '',
      objects:[
        {message :'Hello there 1', id:1},
        {message :'Hello there 2', id:2},
        {message :'Hello there 3', id:3}
      ],
      oneWayText:'hehe',
      twoWayText:'hehe 2.0',

      singleObject:{
        name:'Marcus',
        surname:'Adonis',
      }
    }
  },
  components:{
    InfoComp,
    SlotsComp
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
    color: blue;
  }
  #img{
    object-fit: contain;
    width: 19vw;
    transition: 0.3s;
    filter: blur(1.5px);
  }
  #img:hover{
    width: 21vw;
    cursor: pointer;
    filter: none;
  }
  .hello{
    color: green;
  }
</style>
