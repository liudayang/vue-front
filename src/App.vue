<template>
  <ul>
    <li v-for="(user) in users" :key="user.id">
     <h3> {{user.id}}:{{user.name}}</h3>
     <!-- <hr> -->
    </li>
  </ul>
</template>

<script>
import axios from 'axios';
export default {
  name: 'app',
  data(){
    return {
      users:[]
    }
  },
  mounted(){
    axios.get('/api/users').then(response=>{
    // axios.get('http://localhost:3000/api/users').then(response=>{
      this.users = response.data;
    });
  }
}
</script>

<style>
li{
  border-radius: 10px;
  border: 10px solid tomato;
}
</style>