<template>
   
      <section class="hl_page-creator--settings-group" :class="addClassForAddElementModal">
        <a href="#" class="close-group" id="close-settings-group" @click="$emit('close')"><i class="icon icon-close"></i></a>
        <div class="hl_settings-group">
          <div class="tab-content" id="hl_settings-group-tab">
           
            <div class="tab-pane fade active show" id="seo" role="tabpanel" aria-labelledby="seo-tab">
              <h2>Set element data</h2>
              <div class="seo">
                <div class="form-group">
                  <label>Description</label>
                  <textarea class="form-control" placeholder="Description" rows="3" v-model="text"></textarea>
                </div>


                <div class="form-group">
                    <button type="button" class="btn btn-success btn-block" @click="handleSubmit">Save data</button>
                </div>

              </div>
            </div>



            <div class="tab-pane fade" id="tracking" role="tabpanel" aria-labelledby="tracking-tab">
              <h2>Tracking Code</h2>
              <div class="tracking">
                <div class="form-group">
                  <label>Add HTML/Javascript</label>
                  <textarea class="form-control" placeholder="Add HTML/Javascript here..." rows="5"></textarea>
                </div>
              </div>
            </div>
            <div class="tab-pane fade" id="css" role="tabpanel" aria-labelledby="css-tab">
              <h2>Custom CSS</h2>
              <div class="css">
                <div class="form-group">
                  <label>Add CSS</label>
                  <textarea class="form-control" placeholder="Add custo CSS here..." rows="5"></textarea>
                </div>
              </div>
            </div>
            <div class="tab-pane fade" id="background" role="tabpanel" aria-labelledby="background-tab">
              <h2>Background</h2>
              <div class="background">
                <div class="form-group">
                  <label>Background Image</label>
                  <input type="file">
                </div>
                <div class="form-group">
                  <label>Color</label>
                  <input type="text" class="form-control" placeholder="Color">
                </div>
                <div class="form-group">
                  <label>Background Video</label>
                  <select class="selectpicker" data-width="100%">
                    <option>Off</option>
                    <option>On</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="tab-pane fade" id="typography" role="tabpanel" aria-labelledby="typography-tab">
              <h2>Typography</h2>
              <div class="typography">
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam, expedita. Porro, ea magni doloremque et fuga optio laudantium? Mollitia esse aliquam enim facilis eius natus laborum dolor laboriosam numquam sapiente?
                </p>
              </div>
            </div>
            <div class="tab-pane fade" id="general" role="tabpanel" aria-labelledby="general-tab">
              <h2>General Settings</h2>
              <div class="general">
                <div class="form-group">
                  <label>On Submit Go To</label>
                  <input type="text" class="form-control" placeholder="On Submit Go To">
                </div>
                <div class="form-group">
                  <label>Digital Assets</label>
                  <select class="selectpicker" data-width="100%">
                    <option>- no asset / download -</option>
                    <option>Facebook Strategy Guide</option>
                    <option>Anurli</option>
                    <option>Horatio D Medium</option>
                    <option>Horatio D Light</option>
                    <option>Patient Rush Favicon</option>
                  </select>
                </div>
                <div class="form-group">
                  <label>Affiliate Badge</label>
                  <select class="selectpicker" data-width="100%">
                    <option>Hide</option>
                    <option>Show</option>
                  </select>
                </div>
                <div class="form-group">
                  <label>Search Engines</label>
                  <select class="selectpicker" data-width="100%">
                    <option>Hide</option>
                    <option>Show</option>
                  </select>
                </div>
                <button type="button" class="btn btn-success btn-block">Save Page as Template</button>
              </div>
            </div>
          </div>
        </div>
      </section>
</template>
<script>
export default {
    props: {
        isVisible: {
            required: true
        }
    },
    computed: {
        addClassForAddElementModal() {
            if(this.isVisible) {
                return ['active']
            }
            return []
        }
    },
    data() {
      return {
        text:'',
        url:''
      }
    },
    methods: {
      handleSubmit() {
        let data = { text: this.text, url: this.url }
        this.$emit('submit', data)
        this.text = ''
        this.url = ''
      }
    }
}
</script>
