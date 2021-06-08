<!--  -->
<template>
<div class="check-box-group">
  <slot></slot>
</div>
</template>

<script>
export default {
  name: 'YcCheckBoxGroup',
  props: {
    value: {
      type:Array
    }
  },
  provide() {
    return {
      CheckBoxGroup: this
    }
  }
}
</script>

<style  scoped>

</style>
