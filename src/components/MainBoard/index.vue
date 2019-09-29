<template>
    
      <section class="hl_page-creator--main">
        <OptionMenu 
            @viewTypeChange="viewTypeChange"
            @openAddRowModal="$emit('openAddRowModal')"
            @openAddElementModal="$emit('openAddElementModal')"
        />

        <div class="hl_page-creator--content" :class="addClassForMobileView">
            <PageBoard 
                :pageDetails="pageDetails"
                @addRowBelow="addRowBelow"
                @addElement="addElement"
                @shiftRowUp="shiftRowUp"
                @shiftRowDown="shiftRowDown"
                @handleRowSettingClick="handleRowSettingClick"
                @handleRowCloneclick="handleRowCloneclick"
                @handleRowSaveClick="handleRowSaveClick"
                @handleRowDeleteClick="handleRowDeleteClick"
                @handleDrop="handleDrop"
            />

            <AddRowWidgets 
                v-if="this.pageDetails.length === 0"
                @addRow="addRow"
            />  

          <!-- <section class="hl_page-creator--section" style="background-color: #f4f4f4; padding: 80px 0; text-align: center;">
            <div class="hl_page-creator--actions">
              <div class="move-actions">
                <span data-tooltip="tooltip" data-placement="right" title="Up"><i class="icon icon-arrow-up-2"></i></span>
                <span data-tooltip="tooltip" data-placement="right" title="Down"><i class="icon icon-arrow-down-2"></i></span>
              </div>
              <div class="more-actions">
                <span data-tooltip="tooltip" data-placement="left" title="Settings"><i class="fas fa-cog"></i></span>
                <span data-tooltip="tooltip" data-placement="left" title="Clone"><i class="far fa-eye"></i></span>
                <span data-tooltip="tooltip" data-placement="left" title="Save"><i class="far fa-copy"></i></span>
                <span data-tooltip="tooltip" data-placement="left" title="Delete"><i class="far fa-trash-alt"></i></span>
              </div>
            </div>
            <span class="add-new-section" data-tooltip="tooltip" data-placement="bottom" title="Add New Section"><i class="icon icon-plus"></i></span>
            <div class="hl_page-creator--row">
              <div class="hl_page-creator--actions">
                <div class="move-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Up"><i class="icon icon-arrow-up-2"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Down"><i class="icon icon-arrow-down-2"></i></span>
                </div>
                <div class="more-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Settings"><i class="fas fa-cog"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Clone"><i class="far fa-eye"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Save"><i class="far fa-copy"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
                </div>
              </div>
              <span class="add-new-row" data-tooltip="tooltip" data-placement="bottom" title="Add New Row"><i class="icon icon-plus"></i></span>
              <div class="hl_page-creator--column">
                <div class="hl_page-creator--element">
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
                    <h1>Heading Text Goes Here</h1>
                  </div>
                </div>
                <div class="hl_page-creator--element">
                  <div class="hl_page-creator--actions">
                    <div class="more-actions">
                      <span data-tooltip="tooltip" data-placement="top" title="Move"><i class="fas fa-arrows-alt"></i></span>
                      <span data-tooltip="tooltip" data-placement="top" title="Clone"><i class="far fa-eye"></i></span>
                      <span data-tooltip="tooltip" data-placement="top" title="Save"><i class="far fa-copy"></i></span>
                      <span data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
                    </div>
                  </div>
                  <span class="add-new-element" data-tooltip="tooltip" data-placement="bottom" title="Add New Element"><i class="icon icon-plus"></i></span>
                  <div class="element-container" style="max-width: 700px; margin: 0 auto;">
                    <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quidem architecto quas mollitia voluptates iure consequuntur totam numquam quasi quaerat, iste, libero asperiores optio praesentium autem culpa doloremque laudantium in deleniti,
                      corrupti eaque illo nam quae. Vel nesciunt, libero ipsa similique ipsum ducimus fuga magni. Voluptatum iste pariatur cum doloremque est.</p>
                  </div>
                </div>
              </div>
            </div>
          </section>

          <section class="hl_page-creator--section">
            <div class="hl_page-creator--actions">
              <div class="move-actions">
                <span data-tooltip="tooltip" data-placement="right" title="Up"><i class="icon icon-arrow-up-2"></i></span>
                <span data-tooltip="tooltip" data-placement="right" title="Down"><i class="icon icon-arrow-down-2"></i></span>
              </div>
              <div class="more-actions">
                <span data-tooltip="tooltip" data-placement="left" title="Settings"><i class="fas fa-cog"></i></span>
                <span data-tooltip="tooltip" data-placement="left" title="Clone"><i class="far fa-eye"></i></span>
                <span data-tooltip="tooltip" data-placement="left" title="Save"><i class="far fa-copy"></i></span>
                <span data-tooltip="tooltip" data-placement="left" title="Delete"><i class="far fa-trash-alt"></i></span>
              </div>
            </div>
            <span class="add-new-section" data-tooltip="tooltip" data-placement="bottom" title="Add New Section"><i class="icon icon-plus"></i></span>
            <div class="hl_page-creator--row">
              <div class="hl_page-creator--actions">
                <div class="move-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Up"><i class="icon icon-arrow-up-2"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Down"><i class="icon icon-arrow-down-2"></i></span>
                </div>
                <div class="more-actions">
                  <span data-tooltip="tooltip" data-placement="top" title="Settings"><i class="fas fa-cog"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Clone"><i class="far fa-eye"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Save"><i class="far fa-copy"></i></span>
                  <span data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
                </div>
              </div>
              <span class="add-new-row" data-tooltip="tooltip" data-placement="bottom" title="Add New Row"><i class="icon icon-plus"></i></span>
              <div class="hl_page-creator--column">
                <div class="hl_page-creator--element">
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
                <div class="hl_page-creator--element">
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
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Possimus sint at cum ratione, itaque quas assumenda consequatur, exercitationem ipsa necessitatibus, eaque nemo aliquid quasi. Doloremque dolor pariatur ea quod distinctio?</p>
                  </div>
                </div>
              </div>
              <div class="hl_page-creator--column">
                <div href="#" class="new-element-blank">
                  <span class="btn btn-light6 btn-slim">Add New Element</span>
                </div>
              </div>
              <div class="hl_page-creator--column">
                <div href="#" class="new-element-blank">
                  <span class="btn btn-light6 btn-slim">Add New Element</span>
                </div>
              </div>
            </div>
          </section> -->

        </div>
      </section>
</template>
<script>
import OptionMenu from './OptionMenu'
import AddRowWidgets from './AddRowWidgets'
import PageBoard from './PageBoard'
export default {
    components: {
        OptionMenu,
        AddRowWidgets,
        PageBoard
    },
    props: {
      pageDetails: {
        required: true
      }
    },
    data() {
        return {
            isMobile: false
        }
    },
    computed: {
        addClassForMobileView() {
            if(this.isMobile){
                return ['--mobile']
            } 
            return []
        }
    },
    methods: {
        viewTypeChange(val) {
            this.isMobile = val
        },
        addRow() {
            this.$emit('openAddRowModal')
        },
        addElement(data) {
            this.$emit('addElement', data)
        },
        shiftRowUp(index) {
            this.$emit("shiftRowUp",index)
        },
        shiftRowDown(index) {
            this.$emit("shiftRowDown",index)
        },
        handleRowSettingClick(index) {
            this.$emit("handleRowSettingClick",index)
        },
        handleRowCloneclick(index) {
            this.$emit("handleRowCloneclick",index)
        },
        handleRowSaveClick(index) {
            this.$emit("handleRowSaveClick",index)
        },
        handleRowDeleteClick(index) {
            this.$emit("handleRowDeleteClick",index)
        },
        addRowBelow(index){
            this.$emit("addRowBelow",index)
        },
        handleDrop(data) {
            this.$emit("handleDrop",data)
        }
    }
}
</script>

