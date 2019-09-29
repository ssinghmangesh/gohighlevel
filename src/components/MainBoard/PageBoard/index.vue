
<template>
    <div>
        <Row 
            v-for="(row,rowIndex) in pageDetails" 
            :key="rowIndex"
            :row="row"
            :rowIndex="rowIndex"
            @addElement="addElement"
        />
    
                
    </div>
</template>
<script>
import Row from './Row'
export default {
    components: {
        Row
    },
    props: {
        pageDetails: {
            type: Array,
            required: true
        }
    },
    methods: {
        numberOfColumn(row) {
            return row.column
        },
        addElement(data) {
            this.$emit('addElement', data)
        }
    }
}
</script>

