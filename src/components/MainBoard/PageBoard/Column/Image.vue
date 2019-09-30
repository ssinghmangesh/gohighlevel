<template>
     <div class="hl_page-creator--column">
        <div class="hl_page-creator--element" :class="activeClass" @dblclick="$emit('handleDBClickElement', ELEMENT_TYPE.IMAGE)" @mouseenter="handleMouseOver" @mouseleave="handleMouseOut">
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
              <img :src="text" alt="" height="100%" width="100%"/>
          </div>
        </div>
    </div>
</template>
<script>
import { ELEMENT_TYPE } from '../../../CONSTANTS.js'
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
            return this.column.text || 'https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-260nw-668593321.jpg'
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


