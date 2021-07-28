
<template>
  <h1>Hello</h1>
  <img v-bind:src="imgUrl" />
</template>
<script>
import QRCode from "qrcode";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      imgUrl: "",
    };
  },
  created() {
    QRCode.toDataURL(
      "https://www.redbubble.com/i/mug/Keep-Calm-and-React-JS-by-hipstuff/26255742.9Q0AD"
    )
      .then((url) => {
        console.log(url);
        this.imgUrl = url;
      })
      .catch((err) => {
        console.error(err);
      });
  },
};
</script>
<style scoped>
</style>