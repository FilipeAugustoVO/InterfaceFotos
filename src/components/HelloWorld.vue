
<template>
  <div>
    <h1>Teste</h1>
    <ul>
      <li :key="user.id" v-for="user in users">
        <img :src="user.thumbnailUrl"/>
      {{ user.title }}</li>
    </ul>
  </div>  
</template>


//Dois pontos faz o binding. Binding é dinâmico 

<script>
//import Axios
import axios from 'axios'
export default {
  name: 'InterfaceFotos',
  data: () => ({
    users: []
  }),
  mounted () {
    this.loadUsers()
  },
  methods: {
    async loadUsers () {
      try {
        const { data } = await axios.get('https://jsonplaceholder.typicode.com/photos')
        console.log(data)
        this.users = data
      } catch (e) {
        console.log(e)
      }
    }
  },
}


</script>


