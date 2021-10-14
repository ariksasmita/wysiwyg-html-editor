<template>
  <div v-html="structure"></div>
  <textarea id="" cols="60" rows="10" v-model="structure"></textarea>
</template>

<script>
import { sanitizeUrl } from "@braintree/sanitize-url";
export default {
  name: "Banner",
  props: {
    src: {
      type: String,
      default: "https://picsum.photos/375/125",
    },
    alt: {
      type: String,
      default: "banner",
    },
  },
  computed: {
    imgUrl() {
      return sanitizeUrl(this.src);
    },
    structure() {
      return `
      <div class="banner-wrapper">
        <img src="${this.imgUrl}" alt="${this.alt}" />
        <span class="chevron">&#10095;</span>
      </div>
      `;
    },
  },
};
</script>
<style lang="less" scoped>
.banner-wrapper::after {
  content: "\276F";
  display: block;
  color: white;
}
</style>