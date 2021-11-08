<template>
    <td v-on:click="onClickTd">{{cellData}}</td>
</template>

<script>
export default {
    props: {
        cellData: String,
        rowIndex: Number,
        cellIndex: Number
    },
    data() {
        return {

        }
    },
    methods: {
        onClickTd() {
            if (this.cellData) return;
            const rootData = this.$root.$data;
            this.$set(rootData.tableData[this.rowIndex], this.cellIndex, rootData.turn);
            rootData.turn = rootData.turn === "O"? 'X': 'O';
        }
    }
}
</script>

<style scoped>
    table td {
        border: 1px solid black;
        width: 20px;
        height: 20px;
        text-align: center;
    }
</style>