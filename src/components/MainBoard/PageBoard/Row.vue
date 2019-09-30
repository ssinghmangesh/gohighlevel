<template>
    <div class="hl_page-creator--row" :class="classForActive" @mouseover="handleMouseOver" @mouseout="handleMouseOut">
        <div class="hl_page-creator--actions">
                <div class="move-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Up" @click="$emit('shiftRowUp', rowIndex)"><i class="icon icon-arrow-up-2"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Down" @click="$emit('shiftRowDown', rowIndex)"><i class="icon icon-arrow-down-2"></i></span>
                </div>
                <div class="more-actions">
                  <span data-tooltip="tooltip" data-placement="top" @click="$emit('handleRowSettingClick', rowIndex)" title="Settings"><i class="fas fa-cog"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" @click="$emit('handleRowCloneclick', rowIndex)" title="Clone"><i class="far fa-copy"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" @click="$emit('handleRowSaveClick', rowIndex)" title="Save"><i class="far fa-eye"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" @click="$emit('handleRowDeleteClick', rowIndex)" title="Delete"><i class="far fa-trash-alt"></i></span>
                </div>
        </div>
            <span class="add-new-row" data-tooltip="tooltip" data-placement="bottom" title="Add New Row" @click="$emit('addRowBelow', rowIndex)"><i class="icon icon-plus"></i></span>
              
            <Column
                v-for="(column, colIndex) in row.column"
                :key="colIndex"
                :colIndex="colIndex"
                :column="column"
                :preview="preview"
                @addElement="addElement"
                @handleDrop="handleDrop"
                @handleDBClickElement="handleDBClickElement"
            />
    </div>
</template>
<script>
import Column from './Column'
export default {
    components: {
        Column
    },
    props: {
        row: {
            required: true
        },
        rowIndex: {
            required: true
        },
        preview: {
            type:Boolean,
            required: true
        }
    },
    data() {
        return {
            isActive: false
        }
    },
    computed: {
        classForActive() {
            if(this.isActive) {
                return ['active']
            } 
            return []
        }
    },
    methods: {
        addElement(columnIndex) {
            const { rowIndex } = this
            this.$emit("addElement", {
                rowIndex,
                columnIndex
            })
        },
        handleDrop(index) {
            let data = {
                rowIndex: this.rowIndex,
                columnIndex: index
            }
            this.$emit('handleDrop', data)
        },
        handleDBClickElement(data) {
            let d = {
                ...data,
                rowIndex: this.rowIndex
            }
            this.$emit('handleDBClickElement', d)
        },
        handleMouseOver(e){
            if(!this.preview)
                this.isActive = true
        },
        handleMouseOut(e){
            this.isActive = false
        }
    }
}
</script>

