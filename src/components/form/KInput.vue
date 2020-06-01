<template>
  <div>
    <input type="type" :value="value" @input="onInput">
  </div>
</template>

<script>
import emitter from "@/mixins/emitter";

  export default {
    inheritAttrs: false, //
    mixins: [emitter],
    props: {
      value: {
        type: String,
        default: ''
      },
      type: {
        type: String,
        default: 'text'
      }
    },
    methods: {
      onInput(e) {
        this.$emit('input', e.target.value);
        this.dispatch('KFormItem', "validate");
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>