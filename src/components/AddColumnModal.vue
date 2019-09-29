<template>
      <section class="hl_page-creator--rows-group" :class="addClassForAddRowModal">
        <a href="#" class="close-group" id="close-row-group" @click="$emit('close')"><i class="icon icon-close"></i></a>
        <div class="hl_row-group">
          <div class="tab-content" id="hl_row-group-tab">
            <div class="tab-pane fade active show" id="add-row" role="tabpanel" aria-labelledby="add-row-tab">
              <div class="add-row">
                <h2>Add Row</h2>
                <div class="add-row-body">
                  <div class="row-cards">
                      <ColumnChoice 
                        v-for="(item, index) in columnOptions"
                        :key="index"
                        :item="item"
                        @addRow="addRow"
                      />
                  </div>
                </div>
              </div>
            </div>
            <div class="tab-pane fade" id="manage-rows" role="tabpanel" aria-labelledby="manage-rows-tab">
              <div class="manage-rows">
                <h2>Manage Rows</h2>
                <div class="rows-section-group-wrap">
                  <div class="rows-section-group">
                    <h3>Section</h3>
                    <ul class="rows">
                      <li>
                        <h4>2 Column Row</h4>
                        <div class="actions">
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="fas fa-arrows-alt-v"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-eye"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-copy"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-trash-alt"></i></a>
                        </div>
                      </li>
                    </ul>
                  </div>
                  <div class="rows-section-group">
                    <h3>Section</h3>
                    <ul class="rows">
                      <li>
                        <h4>1 Column Row</h4>
                        <div class="actions">
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="fas fa-arrows-alt-v"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-eye"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-copy"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-trash-alt"></i></a>
                        </div>
                      </li>
                      <li>
                        <h4>1 Column Row</h4>
                        <div class="actions">
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="fas fa-arrows-alt-v"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-eye"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-copy"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-trash-alt"></i></a>
                        </div>
                      </li>
                    </ul>
                  </div>
                  <div class="rows-section-group">
                    <h3>Section</h3>
                    <ul class="rows">
                      <li>
                        <h4>2 Column Row</h4>
                        <div class="actions">
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="fas fa-arrows-alt-v"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-eye"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-copy"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-trash-alt"></i></a>
                        </div>
                      </li>
                    </ul>
                  </div>
                  <div class="rows-section-group">
                    <h3>Section</h3>
                    <ul class="rows">
                      <li>
                        <h4>1 Column Row</h4>
                        <div class="actions">
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="fas fa-arrows-alt-v"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-eye"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-copy"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-trash-alt"></i></a>
                        </div>
                      </li>
                      <li>
                        <h4>1 Column Row</h4>
                        <div class="actions">
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="fas fa-arrows-alt-v"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-eye"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-copy"></i></a>
                          <a href="#" class="btn btn-square-sm btn-light4"><i class="far fa-trash-alt"></i></a>
                        </div>
                      </li>
                    </ul>
                  </div>

                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
</template>
<script>
import ColumnChoice from './ColumnChoice'
export default {
  components: {
    ColumnChoice
  },
    props: {
        isVisible: {
            type: Boolean,
            required: true
        },
    },
    data() {
      return  {
        columnOptions: 10
      }
    },
    computed: {
        addClassForAddRowModal() {
             if(this.isVisible) {
                return [' active']
            }
            return []
        },
    },
    methods: {
      addRow(val) {
        this.$emit("addRow", val)
      },
    }
    
}
</script>

