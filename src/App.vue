<template>
  <h1>{{title}}</h1>
  <p>welcome...</p>
  <!--
  <input type="text" ref="refName">
  <button @click="handleClick">click me</button>
  -->
  <!--demo: use of props.To pass data to Model component
  add the prop attribute header and assign it a name "somestring"
  The string is passed to the Model componentas a prop named header
  <div v-if="showModel"> 
  <Model :header="header" :text="text" theme="sale" @closeThis="toggleModel"/>
  -->
    <div v-if="showModel"> 
      <Model theme="" @closeThis="toggleModel">
        <template v-slot:links>
          <a href="#"> signup now </a>
          <a href="#">more info</a>
        </template>
        <h1>Ninja giveaway</h1>
        <p>Grab your favourite coffee for half price!</p>
        </Model>
    </div>
  

<!--- challenge -->
 <div v-if="showModelTwo"> 
    <Model @closeThis="toggleModelTwo">
      
      <h1>Sign up for our newsletter</h1>
      <p>for updates and promo codes</p>
    </Model>

  </div>
  <button @click.alt="toggleModel"> open model (opt)</button>
  <button @click="toggleModelTwo"> open model two</button>
</template>
<!-- end of challenge -->
<script>
import Model from "./components/Model.vue"

export default {
  name: 'App', //name of component
  components: {Model}, //register child component
  data(){
    return{
      title:  "my first vue app :)",
      showModel: false,
      showModelTwo: false
      }
  },
  methods:{
    toggleModel(){
      this.showModel = !this.showModel
    },
    toggleModelTwo(){
      this.showModelTwo = !this.showModelTwo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
