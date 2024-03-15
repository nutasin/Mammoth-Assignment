<template>
  <button @click="deleteGroup(id)">Delete</button>
</template>

<script>
export default {
    props: ['id'],
    data(){

    },
    methods:{
        deleteGroup(id) {
            this.$emit('removeitem',id)
        },

    }
}
</script>