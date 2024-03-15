<script setup>
import { RouterLink, RouterView } from 'vue-router'
import deleteTodo from './Delete-todo.vue'
import edittodo from './Edit-todo.vue'
</script>

<template>
    <section>
        <input v-model="inputVal" type="text" @keyup.enter="enterKey" placeholder="add new">
        <br><br>

    <div v-for="(group, i) in groups" :key="group.id">

        <span>{{ group }}</span><br>
       
        <input @focus="changeFocus" type="text" placeholder="edit">
        <edittodo :id="i" v-on:updateitem="updateGroup">Update</edittodo>
        <deleteTodo :id="i" v-on:removeitem="deleteGroup"></deleteTodo>

 
    </div>
  </section>
  </template>

  <script>
  export default {
    data(){
            return {
                inputVal: "",
                userInput: [],
                groups: ['testname1', 'testname2', 'testname3'],
        };
    },
    methods:{
        enterKey()
        {
            this.groups.push(this.inputVal);
        },
        deleteGroup(id) {
            this.groups.splice(id,1)
        },
        updateGroup(id) {
            this.groups[id] = this.curEditInput.value;
        },
        changeFocus(e) {
            this.curEditInput = e.target
        }
    }
  }
</script>