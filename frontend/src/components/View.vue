<template>
  <div class="view">
    <p>{{ msg }}</p>
    <modal></modal>
  </div>
</template>

<script>
import Modal from '@/components/Modal'
import Vue from 'vue'
import vmodal from 'vue-js-modal'

Vue.use(vmodal, { 'modal': Modal })

export default {
  name: 'View',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    'modal': Modal
  },
}
</script>

<style scoped>
.view {
  width: 100%;
  height: 100%;
  background-color: whitesmoke;
}
</style>
