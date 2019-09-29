<template>
     <div class="hl_page-creator--column" @dragover.prevent @drop="$emit('handleDrop')">
        <div href="#" class="new-element-blank" @click="$emit('addElement')">
            <span class="btn btn-light6 btn-slim">Add New Element</span>
        </div>
    </div> 
</template>

