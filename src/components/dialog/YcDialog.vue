<!--  -->
<template>
  <transition name="dialog-fade">
    <div class="yc-dialog" v-show="visible">
      <div class="wrapper" @click.self="handleClose">
        <div class="dialog" :style="{ width, top }">
          <div class="header">
            <slot name="title"
              ><span>{{ title }}</span></slot
            >
            <yc-button icon="yc-icon-close" @click="handleClose"></yc-button>
          </div>
          <div class="content"><slot>这是一段信息</slot></div>
          <div class="footer" v-if="$slots.footer">
            <slot name="footer"></slot>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import YcButton from '../button/YcButton.vue'
export default {
  name: 'YcDialog',
  components: { YcButton },
  props: {
    title: {
      type: String,
      default: '提示',
    },
    width: {
      type: String,
      default: '',
    },
    top: {
      type: String,
      default: '',
    },
    visible: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleClose() {
      this.$emit('update:visible', false)
    },
  },
}
</script>

<style scoped>
/* .fade-enter,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave {
  opacity: 1;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s;
} */
.dialog-fade-enter-active {
  animation: fade 0.3s;
}
.dialog-fade-leave-active {
  animation: fade 0.3s reverse;
}

@keyframes fade {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.wrapper {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  min-width: 600px;
  overflow: auto;
  margin: 0;
  z-index: 100;
  background-color: rgba(0, 0, 0, 0.5);
}
.wrapper .dialog {
  background-color: #fff;
  width: 400px;
  height: 200px;
  position: relative;
  left: 50%; /*相对与父元素的宽度*/
  transform: translate(-50%, 0); /*设置水平居中*/
  top: 20vh;
  border-radius: 6px;
  padding: 10px 15px;
}
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.content {
  padding-top: 40px;
  height: 110px;
  font-size: 14px;
  word-wrap: break-word;
}
.footer {
  display: flex;
  justify-content: flex-end;
}
.footer >>> .yc-button {/*深度选择器*/
  margin-left: 10px;
}
</style>
