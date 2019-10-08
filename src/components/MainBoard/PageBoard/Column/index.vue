<template>
    <Heading 
        v-if="type === ELEMENT_TYPE.HEADLINE"
        :column="column"
        :preview="preview"
        @handleDBClickElement="handleDBClickElement"
    />
    <SubHeading 
        v-else-if="type === ELEMENT_TYPE.SUB_HEADLINE"
        :column="column"
        :preview="preview"
        @handleDBClickElement="handleDBClickElement"
    />
    <Paragraph 
        v-else-if="type === ELEMENT_TYPE.PARAGRAPH"
        :column="column"
        :preview="preview"
        @handleDBClickElement="handleDBClickElement"
    />
    <ImageContainer 
        v-else-if="type === ELEMENT_TYPE.IMAGE"
        :column="column"
        :preview="preview"
        @handleDBClickElement="handleDBClickElement"
    />
    <List 
        v-else-if="type === ELEMENT_TYPE.BULLET_LIST"
        :column="column"
        :preview="preview"
        @handleDBClickElement="handleDBClickElement"
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
import { ELEMENT_TYPE } from './../../../CONSTANTS.js'

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
        preview: {
            type:Boolean,
            required: true
        },
        colIndex: {
            type: Number,
            required: true
        },
        column: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            ELEMENT_TYPE
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
        },
        handleDBClickElement(type) {
            let data = { 
                type,
                columnIndex: this.colIndex
            }
            this.$emit('handleDBClickElement', data)
        }
    }

}
</script>

