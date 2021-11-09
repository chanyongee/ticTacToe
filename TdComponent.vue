<template>
    <td v-on:click="onClickTd">{{cellData}}</td>
</template>

<script>
//import Eventbus from './Eventbus';
import store, { CLICK_CELL, CHANGE_TURN } from './store';

export default {
    store,
    props: {
        /* cellData: String, */
        rowIndex: Number,
        cellIndex: Number
    },
    computed: {
        cellData() {
            return this.$store.state.tableData[this.rowIndex][cellIndex];
        }
    },
    data() {
        return {

        }
    },
    methods: {
        onClickTd() {
            this.$store.commit(CLICK_CELL, this.rowIndex, this.cellIndex);
            this.$store.commit(CHANGE_TURN);
            /* if (this.cellData) return;
            const rootData = this.$root.$data;
            this.$set(rootData.tableData[this.rowIndex], this.cellIndex, rootData.turn);
            rootData.turn = rootData.turn === "O"? 'X': 'O'; */
            //Eventbus.$emit('clickTd', this.rowIndex, this.cellIndex);

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
        cursor: pointer;
    }
</style>