<template>
    <div class="hl_page-creator--menu">
          <div class="menu--left">
            <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Back"><i class="fas fa-arrow-left"></i>
            </button>
            <div class="btn-group">
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Desktop" id="page-creator-desktop" @click="$emit('viewTypeChange',false)"><i class="fas fa-desktop"></i>
              </button>
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Mobile" id="page-creator-mobile" @click="$emit('viewTypeChange',true)"><i class="fas fa-mobile-alt"></i>
              </button>
            </div>
            <div class="btn-group">
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Apps"><i class="fas fa-plug"></i>
              </button>
              <div class="dropdown" id="settings-group">
                <button type="button" class="btn btn-light btn-sm dropdown-toggle" aria-haspopup="true" aria-expanded="false" data-toggle="dropdown" data-tooltip="tooltip" data-placement="top" title="Settings"><i class="fas fa-cogs"></i><span class="btn-text">Settings</span>
                </button>
                <div class="dropdown-menu">
                  <div class="nav">
                    <a class="dropdown-item" data-toggle="tab" href="#integrations">Integrations</a>
                    <a class="dropdown-item" data-toggle="tab" href="#seo">SEO Meta Data</a>
                    <a class="dropdown-item" data-toggle="tab" href="#tracking">Tracking Code</a>
                    <a class="dropdown-item" data-toggle="tab" href="#css">Custom CSS</a>
                    <a class="dropdown-item" data-toggle="tab" href="#background">Background</a>
                    <a class="dropdown-item" data-toggle="tab" href="#typography">Typography</a>
                    <a class="dropdown-item" data-toggle="tab" href="#general">General</a>
                  </div>
                </div>
              </div>
              <div class="dropdown">
                <button type="button" class="btn btn-light btn-sm dropdown-toggle" aria-haspopup="true" aria-expanded="false" data-toggle="dropdown" data-tooltip="tooltip" data-placement="top" title="Pop up"><i class="fas fa-external-link-alt"></i><span class="btn-text">Pop up</span>
                </button>
                <div class="dropdown-menu">
                  <a class="dropdown-item" href="#">Show Popup</a>
                  <a class="dropdown-item" href="#">Edit Settings</a>
                </div>
              </div>
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Undo"><i class="fas fa-undo"></i>
              </button>
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Redo" disabled><i class="fas fa-redo"></i>
              </button>
            </div>
          </div>
          <div class="menu--right">
            <div class="btn-group">
              <div class="dropdown" id="section-group">
                <button type="button" class="btn btn-light btn-sm dropdown-toggle" aria-haspopup="true" aria-expanded="false" data-toggle="dropdown" data-tooltip="tooltip" data-placement="top" title="Sections"><i class="fas fa-expand"></i><span class="btn-text">Sections</span>
                </button>
              </div>
              <div class="dropdown" id="row-group">
                <button type="button" class="btn btn-light btn-sm dropdown-toggle" aria-haspopup="true" aria-expanded="false" data-toggle="dropdown" data-tooltip="tooltip" data-placement="top" title="Rows" @click="$emit('openAddRowModal')"><i class="fas fa-bars"></i><span class="btn-text">Rows</span>
                </button>
                <div class="dropdown-menu">
                  <div class="nav">
                    <a class="dropdown-item" data-toggle="tab" href="#add-row">Add Row</a>
                    <a class="dropdown-item" data-toggle="tab" href="#manage-rows">Manage</a>
                  </div>
                </div>
              </div>
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Columns" id="column-group"><i class="fas fa-columns"></i><span class="btn-text">Columns</span>
              </button>
              <div class="dropdown" id="element-group">
                <button type="button" class="btn btn-light btn-sm dropdown-toggle" aria-haspopup="true" aria-expanded="false" data-toggle="dropdown" data-tooltip="tooltip" data-placement="top" title="Elements" @click="$emit('openAddElementModal')"><i class="fas fa-code"></i><span class="btn-text">Elements</span>
                </button>
              </div>
            </div>
            <div class="btn-group">
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Preview" @click="$emit('showPreview')"><i class="far fa-eye"></i><span class="btn-text">Preview</span>
              </button>
              <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="Save" @click="$emit('save')"><i class="far fa-save"></i><span class="btn-text">Save</span>
              </button>
            </div>
          </div>
        </div>
</template>
