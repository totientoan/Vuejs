<template>
    <div class="comp-tab">
        <div class="tabs-title">
            <span>{{ title }}</span>
            <!-- <ion-icon name="heart"></ion-icon> -->
        </div>
        <div class="tabs-content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: 'comp-tabs',
    props: {
        title: String
    },
    data() {
        
    }
}
</script>

<style>
    .tabs-title{
        padding: 15px 30px ;
        display: flex;
        justify-content: space-between;
        border: 2px solid #333;
    }
</style>