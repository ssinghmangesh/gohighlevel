<template>
<div>
    <div v-if="isActive" class="custom-overlay"></div>
    <div v-if="isActive" class="modal fade show" id="client-checkin--modal" tabindex="-1" role="dialog" aria-labelledby="client-checkin--modalLabel" aria-hidden="true" style="display:block">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <div class="modal-header--inner">
            <h5 class="modal-title" id="client-checkin--modalLabel"><i class="icon icon-user --green"></i> Preview</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close" @click="$emit('close')">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
        </div>
        <div class="modal-body">
          <div class="modal-body--inner">
            <PageBoard 
                :preview="true"
                :pageDetails="pageDetails"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>
<script>
import PageBoard from './MainBoard/PageBoard'
export default {
  components: {
    PageBoard
  },
  props: {
    pageDetails: {
      required: true
    },
    isActive: {
      required: true
    }
  }
}
</script>

<style>
.custom-overlay {
  display: block;
    background: rgb(0, 0, 0);
    opacity: 0.5;
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    z-index: 999;
}
</style>

