<template></template>

<script>
import weui from 'weui.js'
import DISTRICTS from './districts';

const DEFAULT_CODE = 100000

export default {
  props: {
    province: { type: [String, Number], default: 110000 },
    city: { type: [String, Number], default: 110100 },
    area: { type: [String, Number], default: 110101 },
    className: { type: String, default: null },
    onlyProvince: { type: Boolean, default: false },
    hideArea: { type: Boolean, default: false },
    cache: { type: Boolean, default: true }
  },
  data() {
    return {
      depth: 3,
      defaultValue: undefined,
      currentProvince: this.determineType(this.province),
      currentCity: this.determineType(this.city),
      currentArea: this.determineType(this.area),
      id: this.cache ? 'default' : Math.random().toString(36).substr(5),
    }
  },
  mounted() {
    let that = this
    this.calculateDepth()

    let picker = weui.picker(that.formatDistricts(), {
      depth: that.depth,
      defaultValue: that.defaultValue,
      onChange: function (result) {
        that.$emit('change', result)
      },
      onConfirm: function (result) {
        that.$emit('confirm', result)
      },
      className: that.className,
      id: that.id,
    })

    document.querySelector('.weui-mask').addEventListener('click', () => {
      that.$emit('cancel')
    })

    document.querySelectorAll('[data-action="cancel"]')[0].addEventListener('click', () => {
      that.$emit('cancel')
    })
  },
  methods: {
    formatDistricts(code = DEFAULT_CODE, time = 1) {
      let districts = [];
      let list = this.getDistricts(code)

      for(let item in list) {
        if(this.getDistricts(item) != null && !this.onlyProvince && !(time == 2 && this.checkHideArea(code))) {
          districts.push({ label: list[item], value: item, children: this.formatDistricts(item, time + 1) })
        } else {
          districts.push({ label: list[item], value: item })
        }
      }

      return districts
    },
    getDistricts(code = DEFAULT_CODE) {
      return DISTRICTS[code] || null
    },
    getAreaCode(name) {
      for(var x in DISTRICTS) {
        for(var y in DISTRICTS[x]) {
          if(name == DISTRICTS[x][y]) {
            return y
          }
        }
      }
    },
    determineType(value) {
      if(typeof value === 'string') {
        return this.getAreaCode(value)
      }

      return value
    },
    calculateDepth() {
      if (this.onlyProvince) {
        this.depth = 1
        this.defaultValue = [this.currentProvince]
      } else if (this.hideArea) {
        this.depth = 2
        this.defaultValue = [this.currentProvince, this.currentCity]
      } else {
        this.defaultValue = [this.currentProvince, this.currentCity, this.currentArea]
      }
    },
    checkHideArea(code) {
      return this.hideArea && code.toString().substr(-2,2) == '00'
    },
  }
}
</script>
