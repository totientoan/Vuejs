<template>
    <div class="list-user">
        <p>List User Component</p>
        <!-- <div v-for="(value, key) in listUser" v-bind:key="key">
            <div v-if="value.active">{{ value.email }}</div>
        </div> -->
        <user 
            v-for="(value,key) in listUser"
            v-bind:key="key"
            v-bind:user="value"
            v-on:deleteUser = "deleteUser"
        />
    </div>
</template>

<script>

import User from './User.vue';
export default {
    name: 'list-user',
    props: {
        listUser: {
            type: Array,
            default: []
        }
    },
    data() {
        return{

        }
    },
    components: {
        User
    },
    methods: {
        deleteUser(data){
            console.log('đây là ',data.id);
            this.$emit('AppdeleteUser',data);
        }

    }
}
</script>

<style>

</style>