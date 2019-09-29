<template>
    <div class="hl_page-creator--row" :class="classForActive" @mouseover="isActive = true" @mouseout="isActive = false">
        <div class="hl_page-creator--actions">
                <div class="move-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Up"><i class="icon icon-arrow-up-2"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Down"><i class="icon icon-arrow-down-2"></i></span>
                </div>
                <div class="more-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Settings"><i class="fas fa-cog"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Clone"><i class="far fa-eye"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Save"><i class="far fa-copy"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
                </div>
        </div>
            <span class="add-new-row" data-tooltip="tooltip" data-placement="bottom" title="Add New Row"><i class="icon icon-plus"></i></span>
              
            <Column
                v-for="(column, colIndex) in row.column"
                :key="colIndex"
                :colIndex="colIndex"
                :column="column"
                @addElement="addElement"
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
        }
    }
}
</script>

