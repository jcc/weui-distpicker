<template>
  <div class="row">
    <div class="blocks">
      <h3 class="text-center">Getting Started</h3>
      <div class="block">
        <h5>Installation</h5>
        <pre class="language-shell code-toolbar"><code class=" language-shell">npm install weui-distpicker --save</code></pre>
        <p>Or</p>
        <pre class="language-shell code-toolbar"><code class=" language-shell">yarn add weui-distpicker --save</code></pre>
      </div>
      <div class="block">
        <h5>Register global component</h5>
          <pre class=" language-javascript code-toolbar"><code class=" language-javascript"><span class="token keyword">import</span> WeuiDistpicker <span class="token keyword">from</span> <span class="token string">'weui-distpicker'</span>

Vue<span class="token punctuation">.</span><span class="token function">component</span><span class="token punctuation">(</span><span class="token string">'weui-distpicker'</span><span class="token punctuation">,</span> WeuiDistpicker<span class="token punctuation">)</span></code></pre>
      </div>
      <div class="block">
        <h5>Register component</h5>
        <pre class=" language-javascript code-toolbar"><code class=" language-javascript"><span class="token keyword">import</span> WeuiDistpicker <span class="token keyword">from</span> <span class="token string">'weui-distpicker'</span>

<span class="token keyword">export</span> <span class="token keyword">default</span> <span class="token punctuation">{</span>
  components<span class="token punctuation">:</span> <span class="token punctuation">{</span> WeuiDistpicker <span class="token punctuation">}</span>
<span class="token punctuation">}</span></code></pre>
      </div>
    </div>
  </div>
</template>
