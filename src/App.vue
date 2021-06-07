<template>
  <div id="app">
    <!-- <yc-input v-model="username" clearable></yc-input>
    <yc-input v-model="password" type='password' showpassword></yc-input> -->
    <!-- <yc-switch v-model="active"></yc-switch> -->
    <!-- <yc-switch v-model="active" active-color="green" inactive-color="red" name="hah"></yc-switch> -->
    <!-- <yc-radio label="1" v-model="gender">男</yc-radio>
    <yc-radio label="0" v-model="gender">女</yc-radio> -->
    <yc-radio-group v-model="gender">
      <yc-radio label="1">男</yc-radio>
      <yc-radio label="0">女</yc-radio>
      <yc-radio label="3">?</yc-radio>
    </yc-radio-group>
  </div>
</template>

<script>
import YcRadio from './components/radio/YcRadio.vue'
import YcRadioGroup from './components/radio/YcRadioGroup.vue'

export default {
  name: 'App',
  data() {
    return {
      gender: '1',
      // username: '',
      // password: '',
      // active: false
    }
  },
  components: {
    YcRadio,
    YcRadioGroup,
  },
  methods: {},
}
</script>

<style>
@import './assets/css/base.css';
@import './assets/fonts/iconfont.css';
</style>
