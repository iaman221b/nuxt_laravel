<template>
  <div>
    <h1>User Index</h1>
    <input type="text" v-model="id">
    <button @click="loadUser">Load User</button>
    
    <no-ssr>
    <v-select v-model="selected" placeholder="Select Category" >
      <!-- :options="{'foo' , 'bar'}" -->
    </v-select>
    </no-ssr>
  </div>
</template>

<script>
export default {
  data(){
    return{
      id: '',
      selected: 'hello'
    }
  },
  methods:{
    loadUser(){
      this.$router.push(`/user/${this.id}`)
    }
  }
}
</script>