<template>
  <div class="test">
    <input v-model="title" placeholder="edit me"><br />
    <h1>{{title}}</h1>
    <p>{{user.firstName+" "+user.lastName}}</p>
    <p v-if="showName" v-text="user.firstName +' '+ user.lastName"></p>
    <p v-else> No one</p>
    <ul>
      <li v-for="item in items" :key="item.title" >{{item.title}}</li>
    </ul>
    <button v-on:click="greet">Say Greeting</button>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <hr>
    <label>First Name: </label><input type="text" v-model="user.firstName">
  
    <br>
    <label>last Name: </label><input type="text" v-model="user.lastName">
  
  <h3>{{fullName}}</h3>
  <h5>{{msg}}</h5>
  </div>
</template>

<script>
export default {
  props:{
    msg:{
      type: String,
      default:'Foobar'
    }
  },
  name: 'test',
  data(){
    return{
      title: "WHO IS TALKING ABOUT ALEXA",
      user: {
        firstName: 'John',
        lastName: 'Casey'

      },
      showName: true,
      items:[
        {title:'item one'},
        {title:'item two'},
        {title:'item three'}

      ]
    }
  },
  methods: {
    greet: function(){
      alert('hey');
    },
    pressKey: function(e){
      console.log(e.target.value);
    },
    enterHit: function(){
      console.log('you hit enter');
    },
    },
    computed: {
      fullName: function(){
        return this.user.firstName+ ' ' +this.user.lastName;
      
    }
  }
}
</script>
<style scoped>

</style>


