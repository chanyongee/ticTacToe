<template>
    <table>
        <tr-component v-for="(rowData, index) in tableData" v-bind:key="index" v-bind:rowIndex="index" v-bind:rowData="rowData"></tr-component>    
    </table>
</template>

<script>
import TrComponent from './TrComponent';

export default ({
    props: {
        tableData: Array
    },
    components: {
        TrComponent
    },
    data() {
        return {

        }
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
