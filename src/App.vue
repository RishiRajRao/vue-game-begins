<template>
  <div>
    <!-- <div>
      <div>I am {{name}}</div>
        <div class="apna-class">This is my identity: {{id}}</div>
        <div v-text="add" :class="fickle && 'apna-class'"></div>
        <div :style="{color:beauty,margin:'200px' ,fontSize:fsize+'px'}">style</div>
        <div :style="style">style</div>
      
      
        <div >
      <p v-if="fsize==200">Hi</p>
      <p v-else-if ="fsize > 200" >just</p>
      <p v-else >checking</p>
        </div>
      
        <div>
      <div v-show ="!isTrue">workholic nerd in love with technology and love to code!</div>
        </div>
      
        <div v-for="actor in actors" :key="actor.name">{{actor.name}}
      <h3 v-for="idea in actor.ideas" :key="idea">{{idea}}</h3>
        </div>
      
        <template>
      
        </template>
      
        <div v-for="(value,key,index) in family" :key="index">{{index}} @{{key}}:{{value}}</div>
      
        <template v-for="dear in dears" >
      <h1 v-if="dear==='Nupur'" :key="dear">name passed:{{dear}}</h1>
        </template>
      
       <div>
         <h1>{{count}}</h1>
      <button v-on:click="decrement($event)">-</button>
        <button @click="increment">+</button>
       </div>
    </div> -->


<!-- <Form/> -->
<Watcher/>


  </div>
</template>

<script>
// import Form from './Form.vue'
import Watcher from './Watcher.vue'
export default {
  name: 'App',
  components:{
    // Form
    Watcher

    
  },
  data(){
    return{
      name:'Rishi',
    id:'workholic-nerd-tech-lover',
    add:'nomad!',
    fickle:false,
    beauty:'orange',
    fsize:'00',
    style:{
      color:'red',
      backgroundColor:'blue'
    },
    isTrue:true,
    actors:[
      {
        name:'rishi',
        ideas:['workhard','patient']
        
      },
      {
        name:'nupur',
        ideas:['love','marraige']
      }
    ],
    family:{
      name:"rahul",
      address:"bettiah",
      post:"845438"
    },

    dears:['rahul','rishi','Nupur','ashish','saurabh'],
    count:0

    };
  },

  methods:{
    increment(event){
      console.log('event check',event)
      return this.count+=1;
    },

    decrement(){
      return this.count-=1;
    }

  }

};
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

.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}

 .apna-class{
    color: red;
    background-color:black;
  }


</style>
