<template>
    <div>TODO</div>
</template>
<script>
import Vue from 'vue'

export Vue.extend({
  props: {
      value: {
        type: Boolean,
        required: true
      },
  },

  data() {
    return {
      show: false,
    }
  },

  watch: {
    value: {
      handler(value) {
        this.show = value
      },
      immediate: true
    },
  },

  methods: {
    onCreateQualityIssue() {
      this.$emit('create', {
        isSafety: false
      })
      this.hide()
    },

    onCreateSafetyIssue() {
      this.$emit('create', {
        isSafety: true
      })
      this.hide()
    },
    onCancel() {
      this.hide()
      this.$emit('cancel')
    },

    hide() {
      this.$emit('input', false)
      this.show = false
    }
  },

})

</script>
<style lang="less" scoped> </style>
