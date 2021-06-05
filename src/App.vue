<template>
  <div id="app">
    <yc-button></yc-button>
    <yc-button type="primary"></yc-button>
    <yc-button type="success"></yc-button>
    <yc-button type="warning"></yc-button>
    <yc-button type="danger"></yc-button>
  </div>
</template>

<script>
import YcButton from './components/button/YcButton.vue'

export default {
  name: 'App',
  components: {
    YcButton,
  },
}
</script>

<style>
@import './assets/css/base.css';
</style>
