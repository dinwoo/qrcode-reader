<template>
  <div class="about">
    <h1>This is an QRCode Reader</h1>
    <qrcode-stream @decode="onDecode"></qrcode-stream>
  </div>
</template>

<script>
// import { QrcodeStream, QrcodeDropZone, QrcodeCapture } from 'vue-qrcode-reader'
export default {
  name: "about",
  methods: {
    onDecode(decodedString) {
      console.log(decodedString);
    },
  },
};
</script>
