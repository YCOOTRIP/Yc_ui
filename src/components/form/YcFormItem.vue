<!--  -->
<template>
  <div class="yc-form-item">
    <label class="label" :style="{ width: this.Form.labelWidth }">{{ label }}</label>
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'YcFormItem',
  inject: ['Form'],
  props: {
    label: {
      type: String,
      default: '',
    },
  },
}
</script>

<style scoped>
.yc-form-item {
  margin-bottom: 25px;
}
.yc-form-item .label {
  text-align: right;
  vertical-align: middle;
  float: left;
  font-size: 14px;
  color: #606266;
  line-height: 40px;
  padding: 0 12px 0 0;
  box-sizing: border-box;
}
.yc-form-item .content {
  line-height: 40px;
  position: relative;
  font-size: 14px;
  overflow: hidden;
}
</style>
