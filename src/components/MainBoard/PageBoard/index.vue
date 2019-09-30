
<template>
    <div>
        <draggable v-model="rows">
            <Row 
                v-for="(row,rowIndex) in rows" 
                :key="rowIndex"
                :row="row"
                :rowIndex="rowIndex"
                :preview="preview"
                @addRowBelow="addRowBelow"
                @addElement="addElement"
                @shiftRowUp="shiftRowUp"
                @shiftRowDown="shiftRowDown"
                @handleRowSettingClick="handleRowSettingClick"
                @handleRowCloneclick="handleRowCloneclick"
                @handleRowSaveClick="handleRowSaveClick"
                @handleRowDeleteClick="handleRowDeleteClick"
                @handleDrop="handleDrop"
                @handleDBClickElement="handleDBClickElement"
            />
        </draggable>
                
    </div>
</template>
<script>
import Vue from 'vue';
import draggable from 'vuedraggable'
import Row from './Row'
export default {
    components: {
        Row,
        draggable
    },
    props: {
        pageDetails: {
            type: Array,
            required: true
        },
        preview: {
            type:Boolean,
            required: true
        }
    },
    data() {
        return {
            rows:[]
        }
    },
    mounted() {
        this.rows = this.pageDetails
    },
    methods: {
        numberOfColumn(row) {
            return row.column
        },
        addElement(data) {
            this.$emit('addElement', data)
        },
        shiftRowUp(index) {
            this.$emit("shiftRowUp",index)
        },
        shiftRowDown(index) {
            this.$emit("shiftRowDown",index)
        },
        handleRowSettingClick(index) {
            this.$emit("handleRowSettingClick",index)
        },
        handleRowCloneclick(index) {
            this.$emit("handleRowCloneclick",index)
        },
        handleRowSaveClick(index) {
            this.$emit("handleRowSaveClick",index)
        },
        handleRowDeleteClick(index) {
            this.$emit("handleRowDeleteClick",index)
        },
        addRowBelow(index){
            this.$emit("addRowBelow",index)
        },
        handleDrop(data) {
            this.$emit("handleDrop",data)
        },
        handleDBClickElement(data) {
            this.$emit('handleDBClickElement', data)
        }
    },
    watch: {
        pageDetails(val) {
            this.rows = val
            //for(let index = 0; index < val.length; index++) {
            //    Vue.set(this.rows, index, val[index])
            //}
        },
        rows(val){
            this.$emit('rowsPositionChanged', val)
        }
    }
}
</script>

