<template>
  <div id="app">
    <!-- <yc-input v-model="username" clearable></yc-input>
    <yc-input v-model="password" type='password' showpassword></yc-input> -->
    <!-- <yc-switch v-model="active"></yc-switch> -->
    <!-- <yc-switch v-model="active" active-color="green" inactive-color="red" name="hah"></yc-switch> -->
    <!-- <yc-radio label="1" v-model="gender">男</yc-radio>
    <yc-radio label="0" v-model="gender">女</yc-radio> -->
    <!-- <yc-radio-group v-model="gender">
      <yc-radio label="1">男</yc-radio>
      <yc-radio label="0">女</yc-radio>
      <yc-radio label="3">?</yc-radio>
    </yc-radio-group> -->
    <!-- <yc-check-box v-model="active">是否选中</yc-check-box>
    <yc-check-box-group v-model="hobby">
      <yc-check-box label="fish"></yc-check-box>
      <yc-check-box label="basketball"></yc-check-box>
      <yc-check-box label="rap"></yc-check-box>
    </yc-check-box-group> -->
    <yc-form :model="model" label-width="80px">
      <yc-form-item label="用户名">
        <yc-input placeholder="请输入用户名" v-model="model.username"></yc-input>
      </yc-form-item>
      <yc-form-item label="select">
        <yc-switch v-model="model.active"></yc-switch>
      </yc-form-item>
    </yc-form>
  </div>
</template>

<script>
import YcForm from '@/components/form/YcForm'
import YcFormItem from '@/components/form/YcFormItem'
import YcInput from './components/input/YcInput.vue'
import YcRadio from './components/radio/YcRadio.vue'
import YcSwitch from './components/switch/YcSwitch.vue'

export default {
  name: 'App',
  data() {
    return {
      model: {
        username: '',
        active: true,
      },
    }
  },
  components: {
    YcFormItem,
    YcForm,
    YcInput,
    YcRadio,
    YcSwitch,
  },
}
</script>
<style>
@import './assets/css/base.css';
@import './assets/fonts/iconfont.css';
</style>
