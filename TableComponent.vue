<template>
    <table>
        <tr-component v-for="(rowData, index) in tableData" v-bind:key="index" v-bind:rowIndex="index"></tr-component>    
    </table>
</template>

<script>
import TrComponent from './TrComponent';
import store from './store';

export default ({
    store,
    computed: {
        tableData() {
            return this.$store.state.tableData;
        }
    },
    components: {
        TrComponent
    },
    methods: {

    }
})
</script>

<style scoped>
    table {
        border-collapse: collapse;
    }

</style>
