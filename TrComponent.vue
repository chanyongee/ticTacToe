<template>
    <tr>
        <td-component v-for="(cellData, index) in rowData" v-bind:key="index" v-bind:cellData="cellData" v-bind:cellIndex="index" v-bind:rowIndex="rowIndex"></td-component>
    </tr>
</template>

<script>
import TdComponent from './TdComponent'

export default ({
    props: {
        rowData: Array,
        rowIndex: Number
    },
    components: {
        TdComponent
    },
    data() {
        return {

        }
    }
})
</script>

<style scoped>

</style>
