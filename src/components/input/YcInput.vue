<!--  -->
<template>
  <div class="yc-input">
    <input
      :type="showpassword ? (PasswordVisible ? 'text' : 'password') : type"
      :name="name"
      :placeholder="placeholder"
      :disabled="disabled"
      class="inner"
      :class="{ 'is-disabled': disabled }"
      :value="value"
      @input="handleInput"
    />
    <span class="suffix" v-if="showSuffix">
      <i class="yc-icon-close" v-if="clearable && value" @click="clear"></i>
      <i class="yc-icon-browse" :class="{'active':PasswordVisible}" v-if="showpassword" @click="handlePassword"></i>
    </span>
  </div>
</template>

<script>
export default {
  name: 'YcInput',
  data() {
    return {
      PasswordVisible: false,
    }
  },
  computed: {
    showSuffix() {
      return this.clearable || this.showpassword
    },
  },
  props: {
    name: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'text',
    },
    placeholder: {
      type: String,
      default: '',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    value: {
      type: String,
      default: '',
    },
    clearable: {
      type: Boolean,
      default: false,
    },
    showpassword: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleInput(e) {
      this.$emit('input', e.target.value)
    },
    clear() {
      this.$emit('input', '')
    },
    handlePassword() {
      this.PasswordVisible = !this.PasswordVisible
    },
  },
}
</script>

<style scoped>
.yc-input {
  width: 250px;
  position: relative;
  font-size: 14px;
  display: inline-block;
}
.yc-input .inner {
  background-color: #fff;
  border: 1px solid #dcdfe6;
  border-radius: 4px;
  color: #606266;
  display: inline-block;
  height: 40px;
  line-height: 40px;
  outline: none;
  padding: 0 15px;
  width: 90%;
}
.yc-input .inner:focus {
  border-color: #409eff;
}
.yc-input .is-disabled {
  background-color: #f5f7fa;
  border-color: #e4e7ed;
  color: #c0c4cc;
  cursor: not-allowed;
}
.suffix {
  position: relative;
  left: -25px;
  cursor: pointer;
}
.suffix .active {
  color: blue;
}
</style>
