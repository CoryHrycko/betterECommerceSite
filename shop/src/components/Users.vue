<template>
  <div class="Users">
      <h1>User's Name</h1>
      <form v-on:submit="addUser" >
          <input type="text" v-model="newUser.name" placeholder="Enter Name">
          <br />
          <input type="text" v-model="newUser.email" placeholder="Enter Email">
          <br />
          <input type="submit" value="Submit" >
          <br />
      </form>
      <ul>
          <li v-for="user in users" :key="user.name">
              {{user.name}}: {{user.email}}
          </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'users',
  data(){
    return{
        newUser: [],
        users:[
            {
            name:'John Doe',
            email:'example@emaple.com',
            contacted: false
            },
            {
            name:'Steve Doe',
            email:'example@emaple.com',
            contacted: false
            },
            {
            name:'Mary Doe',
            email:'example@emaple.com',
            contacted: false
            },
        ]
    }
  },
  methods: {
      addUser: function(e){
          console.log('add');
          e.preventDefault();
      }
  }
}
</script>
<style scoped>

</style>


