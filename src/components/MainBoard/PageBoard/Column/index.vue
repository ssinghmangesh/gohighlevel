<template>
    <Heading 
        v-if="type === 'HEADLINE'"
    />
    <SubHeading 
        v-else-if="type === 'SUB_HEADLINE'"
    />
    <Paragraph 
        v-else-if="type === 'PARAGRAPH'"
    />
    <ImageContainer 
        v-else-if="type === 'IMAGE'"
    />
    <List 
        v-else-if="type === 'BULLET_LIST'"
    />
    <Add v-else
        @addElement="addElement"
        @handleDrop="handleDrop"
    />
</template>
<script>
import Heading from './Heading'
import SubHeading from './SubHeading'
import Paragraph from './Paragraph'
import ImageContainer from './Image'
import List from './List'
import Add from './Add'
export default {
    components: {
        Heading,
        SubHeading,
        Paragraph,
        ImageContainer,
        List,
        Add,
    },
    props: {
        colIndex: {
            type: Number,
            required: true
        },
        column: {
            type: Object,
            required: true
        }
    },
    computed: {
        type() {
            return this.column.type
        }
    },
    methods: {
        addElement() {
            this.$emit('addElement', this.colIndex)
        },
        handleDrop() {
            this.$emit("handleDrop", this.colIndex)
        }
    }

}
</script>

