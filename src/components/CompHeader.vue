<template>
    <header>
        <h1>
            {{ titleHeader }} <br>
            <button v-on:click="changeTitleHeader">Thay đổi từ CompHeader.vue</button>
        </h1>
        <div v-for="(value,key) in listUser" v-bind:key="key">
            <div>value.email</div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'compHeader',
    props: {
        titleHeader: String,
        listUser: {
            type: Array,
            default: []
        }
    },
    data () {
        return {
        text: 'header'
        }
    },
    methods: {
        changeTitleHeader(e){
            //không được thay đổi trực tiếp nên cần gọi hàm
            //kích hoạt bên component cha(App.vue)
            var data = {
                title: 'test -> data truyền từ compnent com'
            }
            //bằng câu lệnh
            this.$emit('changeTitleEvent',data);
        }
    }
}
</script>
<style>

</style>