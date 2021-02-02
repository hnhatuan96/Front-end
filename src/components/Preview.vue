<template>
  <div class="preview-second">
    <p class="preview-second_mess">{{ msg }}</p>
    <button
      class="preview-second_btn"
      v-for="(modal,index) in dataModal"
      :key="index"
      @click="onHandlePopup($refs, index)"
    >
      Open modal {{index + 1}}
    </button>

    <modal
      ref="modalName"
      v-bind:data-header="dataPreviewModal.dataHeader"
      v-bind:data-body="dataPreviewModal.dataBody"
      v-bind:data-footer="dataPreviewModal.dataFooter"
    />
  </div>
</template>

<script>
import Modal from '@/components/Modal'

export default {
  name: 'Preview',
  data () {
    return {
      msg: 'Welcome to My Application',
      dataPreviewModal: {
        dataHeader: '',
        dataBody: '',
        dataFooter: ''
      },
      dataModal: [
        {
          dataHeader: 'This is Header First',
          dataBody: 'This is Body First',
          dataFooter: 'This is Footer First'
        },
        {
          dataHeader: 'This is Header Second',
          dataBody: 'This is Body Second',
          dataFooter: 'This is Footer Second'
        },
        {
          dataHeader: 'This is Header Third',
          dataBody: 'This is Body Third',
          dataFooter: 'This is Footer Third'
        }
      ]
    }
  },
  components: {
    Modal
  },
  methods: {
    onHandlePopup (ref, position) {
      this.dataPreviewModal = this.dataModal[position]
      ref.modalName.openModal()
    }
  }
}
</script>

<style>
.preview-second {
  position: relative;
  width: 100%;
  height: 100%;
}

.preview-second_mess {
  margin-top: 50px;
  margin-bottom: 50px;
}

.preview-second_btn {
  margin-left: 10px;
  margin-right: 10px;
}

.overflow-hidden {
  overflow: hidden;
}
</style>
