<template>
  <modal class="modal">
    This is my modal
  </modal>
</template>

<script>
export default {
  name: 'Modal',
  methods: {
    show () {
      this.$modal.show('modal')
    },
    hide () {
      this.$modal.hide('modal')
    }
  },
  mount () {
    this.show()
  }
}
</script>

<style>
.modal {
  width: 100%;
}
</style>
