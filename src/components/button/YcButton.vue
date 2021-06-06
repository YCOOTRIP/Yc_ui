<!--  -->
<template>
  <div class="yc-button">
    <button :class="[`yc-button-${type}`, { isRound: round, hasBorder: border }]" @click="handleClick">
      <i v-if="icon" :class="icon"></i>
      <span v-if="$slots.default"><slot></slot></span>
    </button>
  </div>
</template>

<script>
export default {
  name: 'YcButton',
  props: {
    border: {
      type: Boolean,
      default: false,
    },
    type: {
      type: String,
      default: 'default',
    },
    round: {
      type: Boolean,
      default: false,
    },
    icon: {
      type: String,
      default: '',
    },
  },
  methods: {
    handleClick(e) {
      this.$emit('click', e)
    },
  },
}
</script>

<style scoped>
.yc-button button {
  border: none;
  padding: 7px 7px;
  border-radius: 3px;
  background-color: #fff;
  transition: all 0.2s ease;
  font-size: 16px;
  line-height: 1;
  text-align: center;
}
.yc-button button:hover {
  cursor: pointer;
  color: #47a2ff;
  background-color: #ecf5ff;
}
.yc-button .yc-button-primary {
  color: #fff;
  background-color: var(--color-primary);
}
.yc-button .yc-button-primary:hover {
  color: #fff;
  background-color: #66b1ff;
}

.yc-button .yc-button-success {
  color: #fff;
  background-color: var(--color-success);
}
.yc-button .yc-button-success:hover {
  color: #fff;
  background-color: #85ce61;
}

.yc-button .yc-button-warning {
  color: #fff;
  background-color: var(--color-warning);
}
.yc-button .yc-button-warning:hover {
  color: #fff;
  background-color: #ebb563;
}

.yc-button .yc-button-danger {
  color: #fff;
  background-color: var(--color-danger);
}
.yc-button .yc-button-danger:hover {
  color: #fff;
  background-color: #f78989;
}
.yc-button .isRound {
  border-radius: 50%;
}
.yc-button .hasBorder {
  border: 1px solid #dcdfe6;
}
.yc-button [class*='yc-icon-'] + span {
  margin-left: 7px;
}
</style>
