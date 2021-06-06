<template>
  <div id="app">
    <!-- <yc-button type="primary" @click="dialogVisible = true">确定</yc-button> -->
    <!-- <yc-dialog title="温馨提示"></yc-dialog> -->
    <!-- <yc-dialog width="30%" top="35vh" :visible.sync="dialogVisible">
      <template #title>
        温馨提示
      </template>
      <template #footer>
        <yc-button border @click="dialogVisible = false">取消</yc-button>
        <yc-button border type="primary" @click="dialogVisible = false">确定</yc-button>
      </template>
    </yc-dialog> -->
  </div>
</template>

<script>
import YcButton from './components/button/YcButton.vue'
import YcDialog from './components/dialog/YcDialog.vue'

export default {
  name: 'App',
  data() {
    return {
      dialogVisible: false,
    }
  },
  components: {
    YcButton,
    YcDialog,
  },
  methods: {
    fn() {},
  },
}
</script>

<style>
@import './assets/css/base.css';
@import './assets/fonts/iconfont.css';
</style>
