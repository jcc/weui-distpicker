<template>
  <div class="row">
    <div class="example">
      <h5>Default Value</h5>
      <div class="example-box">
        <div class="box-left d-flex align-items-baseline">
          <div class="col-md-6">
            <button class="btn btn-info" @click="show=true">Show</button>
            <distpicker
              v-if="show"
              :province="message.province"
              :city="message.city"
              :area="message.area"
              @confirm="onConfirm"
              @cancel="onCancel"></distpicker>
          </div>
          <div class="content-show col-md-5">
            <pre><code>{{ message }}</code></pre>
          </div>
        </div>
        <div class="box-right col-md-12" v-if="showCode">
<pre class=" language-javascript code-toolbar"><code class=" language-javascript"><span class="token operator">&lt;</span>teamplate<span class="token operator">&gt;</span>
  <span class="token operator">&lt;</span>weui-distpicker
    <span class="token punctuation">:</span>province<span class="token operator">=</span><span class="token string">"message.province"</span>
    <span class="token punctuation">:</span>city<span class="token operator">=</span><span class="token string">"message.city"</span>
    <span class="token punctuation">:</span>area<span class="token operator">=</span><span class="token string">"message.area"</span><span class="token operator">&gt;</span><span class="token operator">&lt;</span><span class="token operator">/</span>weui-distpicker<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span><span class="token operator">/</span>template<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>script<span class="token operator">&gt;</span>
<span class="token keyword">import</span> WeuiDistpicker <span class="token keyword">from</span> <span class="token string">'weui-distpicker'</span>

<span class="token keyword">export</span> <span class="token keyword">default</span> <span class="token punctuation">{</span>
  components<span class="token punctuation">:</span> <span class="token punctuation">{</span> WeuiDistpicker <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token function">data</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">{</span>
      message<span class="token punctuation">:</span> <span class="token punctuation">{</span>
        province<span class="token punctuation">:</span> <span class="token string">'广东省'</span><span class="token punctuation">,</span>
        city<span class="token punctuation">:</span> <span class="token string">'广州市'</span><span class="token punctuation">,</span>
        area<span class="token punctuation">:</span> <span class="token string">'海珠区'</span>
      <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token punctuation">}</span>
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
        province: '广东省',
        city: '广州市',
        area: '海珠区'
      },
    }
  },
  methods: {
    onChange(data) {
      console.log(data)
    },
    onConfirm(data) {
      this.message.province = data[0].label
      this.message.city = data.length >= 2 ? data[1].label : ''
      this.message.area = data.length == 3 ? data[2].label : ''
      this.show = false
    },
    onCancel() {
      this.show = false
    },
  },
}
</script>
