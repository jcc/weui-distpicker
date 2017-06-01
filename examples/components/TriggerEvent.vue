<template>
  <div class="row">
    <div class="example">
      <h5>Trigger Event</h5>
      <div class="example-box">
        <div class="box-left d-flex align-items-baseline">
          <div class="col-md-6">
            <button class="btn btn-info" @click="show=true">Show</button>
            <distpicker v-if="show" @change="onChange" @confirm="onConfirm" @cancel="onCancel"></distpicker>
          </div>
          <div class="content-show col-md-5">
            <pre><code>{{ message }}</code></pre>
          </div>
        </div>
        <div class="box-right col-md-12" v-if="showCode">
<pre class=" language-javascript code-toolbar"><code class=" language-javascript"><span class="token operator">&lt;</span>teamplate<span class="token operator">&gt;</span>
  <span class="token operator">&lt;</span>weui<span class="token operator">-</span>distpicker @change<span class="token operator">=</span><span class="token string">"onChange"</span> @confirm<span class="token operator">=</span><span class="token string">"onConfirm"</span> @cancel<span class="token operator">=</span><span class="token string">"onCancel"</span><span class="token operator">&gt;</span><span class="token operator">&lt;</span><span class="token operator">/</span>weui<span class="token operator">-</span>distpicker<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span><span class="token operator">/</span>template<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>script<span class="token operator">&gt;</span>
<span class="token keyword">import</span> WeuiDistpicker <span class="token keyword">from</span> <span class="token string">'weui-distpicker'</span>

<span class="token keyword">export</span> <span class="token keyword">default</span> <span class="token punctuation">{</span>
  components<span class="token punctuation">:</span> <span class="token punctuation">{</span> WeuiDistpicker <span class="token punctuation">}</span><span class="token punctuation">,</span>
  methods<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    <span class="token function">onChange</span><span class="token punctuation">(</span>data<span class="token punctuation">)</span> <span class="token punctuation">{</span>
      <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">'change'</span><span class="token punctuation">)</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token function">onConfirm</span><span class="token punctuation">(</span>data<span class="token punctuation">)</span> <span class="token punctuation">{</span>
      <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">'confirm'</span><span class="token punctuation">)</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token function">onCancel</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
      <span class="token function">alert</span><span class="token punctuation">(</span><span class="token string">'cancel'</span><span class="token punctuation">)</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span>
<span class="token operator">&lt;</span><span class="token operator">/</span>script<span class="token operator">&gt;</span></code></pre>
        </div>
        <div class="box-footer" @click="showCode = !showCode">
          {{ showCode ? 'Hide Code' : 'Show Code' }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Distpicker from '../../src/Distpicker'

export default {
  components: { Distpicker },
  data() {
    return {
      show: false,
      showCode: false,
      message: {
        province: '',
        city: '',
        area: ''
      },
    }
  },
  methods: {
    onChange(data) {
      alert('change')
      console.log(data)
    },
    onConfirm(data) {
      alert('confirm')
      this.message.province = data[0].label
      this.message.city = data.length >= 2 ? data[1].label : ''
      this.message.area = data.length == 3 ? data[2].label : ''
      this.show = false
    },
    onCancel() {
      alert('cancel')
      this.show = false
    },
  },
}
</script>
