<!--  -->
<template>
  <label class="yc-checkbox" :class="{ 'is-checked': isChecked }">
    <span class="input">
      <span class="inner"></span>
      <input type="checkbox" class="original" :name="name" v-model="model" :value="label" />
    </span>
    <span class="label">
      <slot>{{ label }}</slot>
    </span>
  </label>
</template>

<script>
export default {
  name: 'YcCheckBox',
  inject: {
    CheckBoxGroup: {
      default: '',
    },
  },
  computed: {
    isGroup() {
      return !!this.CheckBoxGroup
    },
    model: {
      get() {
        return this.isGroup ? this.CheckBoxGroup.value : this.value
      },
      set(value) {
        return this.isGroup ? this.CheckBoxGroup.$emit('input', value) : this.$emit('input', value)
      },
    },
    isChecked() {
      return this.isGroup ? this.model.includes(this.label) : this.model
    },
  },
  props: {
    label: {
      type: String,
      default: '',
    },
    name: {
      type: String,
      default: '',
    },
    value: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped>
.yc-checkbox {
  color: #606266;
  font-weight: 500;
  font-size: 14px;
  position: relative;
  cursor: pointer;
  display: inline-block;
  white-space: nowrap;
  user-select: none;
  margin-right: 30px;
}
.yc-checkbox .input {
  white-space: nowrap;
  cursor: pointer;
  outline: none;
  display: inline-block;
  line-height: 1;
  position: relative;
  vertical-align: middle;
}
.yc-checkbox .input .inner {
  display: inline-block;
  position: relative;
  border: 1px solid #dcdfe6;
  border-radius: 2px;
  box-sizing: border-box;
  width: 14px;
  height: 14px;
  background-color: #fff;
  z-index: 1;
}
.yc-checkbox .input .inner::after {
  box-sizing: content-box;
  content: '';
  border: 1px solid #fff;
  border-left: 0;
  border-top: 0;
  height: 7px;
  left: 4px;
  position: absolute;
  top: 1px;
  transform: rotate(45deg) scaleY(0);
  width: 3px;
  transition: transform 0.15s ease-in 0.05s;
  transform-origin: center;
}
.yc-checkbox .input .original {
  opacity: 0;
  outline: none;
  position: absolute;
  left: 10px;
  margin: 0;
  width: 0;
  height: 0;
  z-index: -1;
}
.yc-checkbox .label {
  display: inline-block;
  padding-left: 10px;
  line-height: 19px;
  font-size: 14px;
}
.yc-checkbox.is-checked .input .inner {
  background-color: #409eff;
  border-color: #409eff;
}
.yc-checkbox.is-checked .input .inner::after {
  transform: rotate(45deg) scaleY(1);
}
.yc-checkbox.is-checked .label {
  color: #409eff;
}
</style>
