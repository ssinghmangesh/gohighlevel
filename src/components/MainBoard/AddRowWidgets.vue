<template>
    <section class="hl_page-creator--section" :class="classForActive" @mouseenter="isActive = true" @mouseleave="isActive = false">
      <div class="hl_page-creator--actions">
        <div class="move-actions">
          <span data-tooltip="tooltip" data-placement="right" title="Up"><i class="icon icon-arrow-up-2"></i></span>
          <span data-tooltip="tooltip" data-placement="right" title="Down"><i
            class="icon icon-arrow-down-2"></i></span>
        </div>
        <div class="more-actions">
          <span data-tooltip="tooltip" data-placement="left" title="Settings"><i class="fas fa-cog"></i></span>
          <span data-tooltip="tooltip" data-placement="left" title="Clone"><i class="far fa-eye"></i></span>
          <span data-tooltip="tooltip" data-placement="left" title="Save"><i class="far fa-copy"></i></span>
          <span data-tooltip="tooltip" data-placement="left" title="Delete"><i class="far fa-trash-alt"></i></span>
        </div>
      </div>
      <span class="add-new-section" data-tooltip="tooltip" data-placement="bottom" title="Add New Section"><i class="icon icon-plus"></i></span>
      <div href="#" class="new-row-blank">
        <span class="btn btn-light5 btn-slim">Add New Row</span>
      </div>
    </section>
</template>
<script>
export default {
    props: {
    },
    data() {
        return {
            isActive: false
        }
    },
    computed: {
        classForActive() {
            if(this.isActive){
                return ['active']
            }
            return []
        }
    }
}
</script>

