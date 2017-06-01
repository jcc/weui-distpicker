<p align="center">
<img src="https://pigjian.com/images/weui-distpicker.png" alt="Powered By Jiajian Chan" width="160">
</p>

<p align="center">A flexible, highly available district selector for picking provinces, cities and districts of China base on weui.js.</p>

# Weui - Distpicker

Here is [documents](https://weui-distpicker.iline.co/)

[Without Weui.js](https://github.com/jcc/v-distpicker)

## Installation

```javascript
npm install weui-distpicker --save
```

Or

```javascript
yarn add weui-distpicker --save
```

## Usage

**Register component**

Registe global component:

```javascript
import WeuiDistpciker from 'weui-distpicker'

Vue.component('weui-distpicker', WeuiDistpciker)
```

Registe component:

```javascript
import WeuiDistpciker from 'weui-distpicker'

export default {
  components: { WeuiDistpciker }
}
```

**Simple usage**

```javascript
<template>
  <weui-distpciker></weui-distpicker>
</template>

<script>
import WeuiDistpciker from 'weui-distpicker'

export default {
  components: { WeuiDistpciker },
}
</script>
```

> Please check the [Documentation](https://weui-distpicker.iline.co/) more

## Contributors

- [Jiajian Chan](http://github.com/jcc)

## License

The plugin is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
