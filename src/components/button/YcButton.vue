<!--  -->
<template>
  <div class="yc-button">
    <button :class="[`yc-button-${type}`]">
      <slot>默认文字</slot>
    </button>
  </div>
</template>

<script>
export default {
  name: 'YcButton',
  props: {
    type: {
      type: String,
      default: '',
    },
  },
}
</script>

<style scoped>
.yc-button button {
  padding: 10px 7px;
  border-radius: 3px;
  border: 1px solid #dcdfe6;
  background-color: #fff;
  transition: all 0.2s ease;
}
.yc-button button:hover {
  cursor: pointer;
  color: #47a2ff;
  background-color: #ecf5ff;
  border: 1px solid #c6e2ff;
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
</style>
