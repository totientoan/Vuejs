<template>
    <div class="demo-slot">
        <comp-tabs title="Tiêu đề của tab">
            <ul class="tabs-header">
                <li v-for="(value, index) in tabHeader" v-bind:key="index" v-on:click="setTabActive(index)">{{ value.text }}</li>
            </ul>
            <div class="tab-content tab1" v-if="tabActive === 0">
                <p>
                    Tab1 Since components are reusable Vue instances, 
                    they accept the same options as new Vue, such as data, 
                    computed, watch, methods, and lifecycle hooks. The only 
                    exceptions are a few root-specific options like el.
                </p>
            </div>
            <div class="tab-content tab2" v-if="tabActive === 1">
                <p>
                    Tab2 Since components are reusable Vue instances, 
                    they accept the same options as new Vue, such as data, 
                    computed, watch, methods, 
                </p>
            </div>
            <div class="tab-content tab3" v-if="tabActive === 2">
                <p>
                    Tab3 Since components , and lifecycle hooks. The only 
                    exceptions are a few root-specific options like el.
                </p>
            </div>
        </comp-tabs>
    </div>
</template>

<script>
import CompTabs from "./CompTabs.vue";
export default {
    name: "demo-slot",
    data() {
        return {
            tabHeader: [
                { text: 'tab1' },
                { text: 'tab2' },
                { text: 'tab3' },
            ],
            tabActive: 0
        }     
    },
    components: {
        CompTabs
    },
    methods: {
        setTabActive(index){
            this.tabActive = index;
        }
    }
}
</script>

<style>
    .demo-slot {
        margin-top: 100px;
        padding: 100px 30px;
        border: 1px solid #000;
    }
    .tabs-header{
        margin: 0;
        padding: 0;
        display: flex;
        list-style-type: none;
    }
    .tabs-header li{
        padding: 8px 15px;
        background-color: #ccc;
    }
    .tabs-header li:hover{
        color: #ffff;
        background-color: #333;
    }
</style>