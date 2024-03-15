<template>
    <button @click="updateGroup(id)">Edit</button>
  </template>
  
  <script>
  export default {
      props: ['id'],
      data(){
  
      },
      methods:{
        updateGroup(id) {
              this.$emit('updateitem',id)
          },
  
      }
  }
  </script>