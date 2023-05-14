<script setup lang="ts">
import QRCodeVue3 from 'qrcode-vue3'
import { ref } from 'vue'

const data = ref('Hello world')
</script>

<template>
  <body>
    <div>Input any text here: <input v-model="data" /></div>
    <div style="margin: 20px">
      <QRCodeVue3
        :width="400"
        :height="400"
        :value="data"
        :key="data"
        :qr-options="{
          errorCorrectionLevel: 'H'
        }"
        :image-options="{ hideBackgroundDots: true, imageSize: 0.4, margin: 10 }"
        :corners-square-options="{ type: 'dot', color: '#34495E' }"
        :corners-dot-options="{
          type: undefined,
          color: '#41B883'
        }"
        :dots-options="{
          type: 'dots',
          color: '#41B883',
          gradient: {
            type: 'linear',
            rotation: 0,
            colorStops: [
              { offset: 0, color: '#41B883' },
              { offset: 1, color: '#34495E' }
            ]
          }
        }"
        image="logo.svg"
        :download="false"
      />
    </div>
    <div>Data:{{ data }}</div>
    <div>Code:</div>
    <code>
      import QRCodeVue3 from 'qrcode-vue3' &lt;QRCodeVue3 :width=&quot;400&quot;
      :height=&quot;400&quot; :value=&quot;data&quot; :key=&quot;data&quot; :qr-options=&quot;{
      errorCorrectionLevel: &#039;H&#039; }&quot; :image-options=&quot;{ hideBackgroundDots: true,
      imageSize: 0.4, margin: 10 }&quot; :corners-square-options=&quot;{ type: &#039;dot&#039;,
      color: &#039;#34495E&#039; }&quot; :corners-dot-options=&quot;{ type: undefined, color:
      &#039;#41B883&#039; }&quot; :dots-options=&quot;{ type: &#039;dots&#039;, color:
      &#039;#41B883&#039;, gradient: { type: &#039;linear&#039;, rotation: 0, colorStops: [ {
      offset: 0, color: &#039;#41B883&#039; }, { offset: 1, color: &#039;#34495E&#039; } ] } }&quot;
      image=&quot;logo.svg&quot; :download=&quot;false&quot; /&gt;
    </code>
    <ul>
      <li><a href="https://qrcode-vue3-sample.vercel.app/">DEMO</a></li>
      <li><a href="https://github.com/scholtz/qrcode-vue3-sample/blob/master/src/App.vue">DEMO Source code</a></li>
      <li><a href="https://github.com/scholtz/qrcode-vue3">QR Code library source code</a></li>
    </ul>
  </body>
</template>
