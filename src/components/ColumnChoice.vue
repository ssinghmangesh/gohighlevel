<template>
    <div class="row-card" @click="$emit('addRow',item)">
      <div class="icon">
        <i class="fas fa-columns"></i>
      </div>
      <h5>{{ item }} Column</h5>
    </div>
</template>
<script>
export default {
    props: {
        item: {
            required: true
        }
    }
}
</script>

