<template>
  <div class="container">
    <logo></logo>
    <get-start></get-start>
    <usage></usage>
    <attributes></attributes>
    <events></events>
    <footbar></footbar>
  </div>
</template>

<script>
import Logo from './components/Logo'
import GetStart from './components/GetStart'
import Usage from './components/Usage'
import Attributes from './components/Attributes'
import Events from './components/Events'
import Footbar from './components/Footer'
import './css/styles.css'

export default {
  components: {
    Logo,
    GetStart,
    Usage,
    Attributes,
    Events,
    Footbar,
  },
  data() {
    return {
      showDist: false,
      showDist1: false,
      message: {
        province: '广东省',
        city: '佛山市',
        area: ''
      },
    }
  },
}
</script>
