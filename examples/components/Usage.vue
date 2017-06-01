<template>
  <div class="row">
    <div class="blocks">
      <h3 class="text-center mt-4">How to use</h3>
      <div class="block">
        <base-usage></base-usage>
        <default-value></default-value>
        <only-province></only-province>
        <hide-area></hide-area>
        <trigger-event></trigger-event>
      </div>
    </div>
  </div>
</template>

<script>
import BaseUsage from './BaseUsage'
import DefaultValue from './DefaultValue'
import OnlyProvince from './OnlyProvince'
import HideArea from './HideArea'
import TriggerEvent from './TriggerEvent'

export default {
  components: {
    BaseUsage,
    DefaultValue,
    OnlyProvince,
    HideArea,
    TriggerEvent,
  }
}
</script>
