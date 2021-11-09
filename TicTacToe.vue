<template>
    <div>
        <div>{{turn}}님의 턴입니다</div>
        <table-component></table-component>
        <div v-if="winner">{{winner}}님의 승리!</div>
    </div>

</template>

<script>
import TableComponent from './TableComponent'
import store from './store';
import { mapState } from 'vuex';
//import Eventbus from './Eventbus';

export default ({
    store,
    components: {
        TableComponent
    },
    computed: {
        ...mapState(['winner', 'turn'])
    },
    methods: {
        /* onClickTd(rowIndex, cellIndex) {
            this.$set(this.tableData[rowIndex], cellIndex, this.turn);
            this.turn = this.turn === "O"? 'X': 'O';
        }, */

    },
    /* created() {
        Eventbus.$on('clickTd', this.onClickTd);
    } */
})
</script>

<style scoped>

</style>
