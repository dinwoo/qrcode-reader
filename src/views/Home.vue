<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <qrcodeScanner v-bind:qrbox="250" v-bind:fps="10" style="width: 500px;">
    </qrcodeScanner>
  </div>
</template>

<script src="https://unpkg.com/html5-qrcode/minified/html5-qrcode.min.js"></script>
<script>
import qrcodeScanner from "../components/QrcodeScanner.vue";

export default {
  name: "Home",
  components: {
    qrcodeScanner,
  },
  data() {
    return {
      header: "Html5-qrcode using vue.js",
      result: "",
    };
  },
  created: function() {
    this.$root.$on(
      "decodedQrCode",
      function(qrCodeMessage) {
        this.decodedMessage = qrCodeMessage;
      }.bind(this)
    );
  },
};
</script>
