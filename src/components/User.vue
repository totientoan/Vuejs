<template>
    <div id="user">
        <h3>{{ user.email }}</h3>
        <button 
            v-on:click="handleDelete"
            class="delete">Delete</button>
    </div>
</template>

<script>
export default {
    name: 'user',
    props: {
        user: Object,
        default: null
    },
    data() {
        return{

        }
    },
    methods: {
        handleDelete(data){
            var data ={
                id: this.user.id
            }
            this.$emit('deleteUser',data);
        }
    }
}
</script>

<style>
    .user{
        border: 1px;
    }
</style>