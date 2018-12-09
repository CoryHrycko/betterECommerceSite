<template>
  <div class="test">
    <input type="text" v-model="title"><br>
    <h1>{{title}}</h1>
    <p>{{user.firstName+" "+user.lastName}}</p>
    <p v-if="showName" v-text="user.firstName +' '+ user.lastName"></p>
    <p v-else> No one</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
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
  }
}
</script>
<style scoped>

</style>


