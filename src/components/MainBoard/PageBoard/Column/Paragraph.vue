<template>
     <div class="hl_page-creator--column">
        <div class="hl_page-creator--element" :class="activeClass" @dblclick="$emit('handleDBClickElement', ELEMENT_TYPE.PARAGRAPH)"  @mouseenter="handleMouseOver" @mouseleave="handleMouseOut">
          <div class="hl_page-creator--actions">
            <div class="more-actions">
              <span data-tooltip="tooltip" data-placement="top" title="Move"><i class="fas fa-arrows-alt"></i></span>
              <span data-tooltip="tooltip" data-placement="top" title="Clone"><i class="far fa-eye"></i></span>
              <span data-tooltip="tooltip" data-placement="top" title="Save"><i class="far fa-copy"></i></span>
              <span data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
            </div>
          </div>
          <span class="add-new-element" data-tooltip="tooltip" data-placement="bottom" title="Add New Element"><i class="icon icon-plus"></i></span>
          <div class="element-container">
            <p>{{ text }}</p>
          </div>
        </div>
    </div>
</template>
<script>
import { ELEMENT_TYPE, DEFAULT_VALUE } from '../../../CONSTANTS.js'
export default {
    props: {
        column: {
            required: true
        }
    },
    data() {
        return {
            isActive: false,
            ELEMENT_TYPE
        }
    },
    computed: {
        activeClass() {
            if(this.isActive) {
                return ['active']
            }
            return []
        },
        text() {
            return this.column.text || DEFAULT_VALUE.TEXT
        }
    },
    methods: {
        handleMouseOver(){
            if(!this.preview){
                this.isActive = true
            }
        },
        handleMouseOut(){
            this.isActive = false
        }

    }
}
</script>


