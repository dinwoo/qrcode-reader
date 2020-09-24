<template>
  <div id="qr-code-full-region"></div>
</template>

<script src="https://unpkg.com/html5-qrcode/minified/html5-qrcode.min.js"></script>
<script>
export default {
  name: "qrcode-scanner",
  props: {
    qrbox: Number,
    fps: Number,
  },
  mounted() {
    var $this = this;
    var config = { fps: this.fps ? this.fps : 10 };
    if (this.qrbox) {
      config["qrbox"] = this.qrbox;
    }

    function onScanSuccess(qrCodeMessage) {
      $this.$root.$emit("decodedQrCode", qrCodeMessage);
    }

    var html5QrcodeScanner = new Html5QrcodeScanner(
      "qr-code-full-region",
      config
    );
    html5QrcodeScanner.render(onScanSuccess);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
