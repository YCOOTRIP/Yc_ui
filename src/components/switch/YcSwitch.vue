<!--  -->
<template>
  <div class="yc-switch" :class="{ isCheck: value }" @click="handleClick">
    <input type="checkbox" class="switch-input" :name="name" ref="inputRef" />
    <span class="core" ref="coreRef">
      <span class="button"></span>
    </span>
  </div>
</template>

<script>
export default {
  name: 'YcSwitch',
  props: {
    value: {
      type: Boolean,
      default: false,
    },
    activeColor: {
      type: String,
      default: '',
    },
    inactiveColor: {
      type: String,
      default: '',
    },
    name: {
      type: String,
      default: '',
    },
  },
  methods: {
    handleClick() {
      this.$emit('input', !this.value)
      // 等待value值(父组件)更新后
      this.$nextTick(() => {
        this.setCoreColor()
        this.$refs.inputRef.checked = this.value
      })
    },
    setCoreColor() {
      if (this.activeColor || this.inactiveColor) {
        let color = this.value ? this.activeColor : this.inactiveColor
        this.$refs.coreRef.style.borderColor = color
        this.$refs.coreRef.style.backgroundColor = color
      }
    },
  },
  mounted() {
    this.setCoreColor()
    this.$refs.inputRef.checked = this.value
  },
}
</script>

<style scoped>
.yc-switch {
  display: inline-flex;
  align-items: center;
  position: relative;
  font-size: 14px;
  line-height: 20px;
  height: 20px;
  vertical-align: middle;
}

.yc-switch .switch-input {
  position: absolute;
  width: 0;
  height: 0;
  opacity: 0;
}
.yc-switch .core {
  margin: 0;
  display: inline-block;
  position: relative;
  width: 40px;
  height: 20px;
  border: 1px solid #dcdfe6;
  outline: none;
  border-radius: 10px;
  box-sizing: border-box;
  background: #dcdfe6;
  cursor: pointer;
  transition: border-color 0.3s, background-color 0.3s;
  vertical-align: middle;
}
.yc-switch .core .button {
  position: absolute;
  top: 1px;
  left: 1px;
  border-radius: 100%;
  transition: all 0.3s;
  width: 16px;
  height: 16px;
  background-color: #fff;
}
.isCheck .core {
  border-color: #409eff;
  background-color: #409eff;
}
.isCheck .core .button {
  transform: translateX(20px);
}
</style>
