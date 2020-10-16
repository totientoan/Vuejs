<template>
    <div class="demo-ref">
        <button 
            class="avatar"
            v-on:click="handleClickInputFile">
            Thay đổi Avatar
        </button>
        <input  
                ref="fileInputAvatar"
                type="file"
                style="display: none;">
    </div>
</template>

<script>
export default {
    name: "demo-ref",
    data() {
        return {

        }
    },
    methods: {
        handleClickInputFile(e){
            this.$refs.fileInputAvatar.click();
            // console.log(this.$refs.fileInputAvatar);
        }
    }
}
</script>
<style>
    .demo-ref {
        margin-top: 100px;
        padding: 100px 30px;
        border: 1px solid #000;
    }
    .avatar {
        color: #ffff;
        padding: 12px 15px;
        border: 2px solid #333;
        background-color: #333;
        transition: all .3s ease;
    }
    .avatar:hover {
        color: #333;
        background-color: #fff;
    }
</style>