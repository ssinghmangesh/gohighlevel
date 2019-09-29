<template>
    <div class="hl_page-creator--column">
        <div class="hl_page-creator--element" :class="activeClass"  @mouseenter="isActive = true" @mouseleave="isActive = false">
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
            <h3>Heading Text Goes Here</h3>
          </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            isActive: false
        }
    },
    computed: {
        activeClass() {
            if(this.isActive) {
                return ['active']
            }
            return []
        }
    }
}
</script>

