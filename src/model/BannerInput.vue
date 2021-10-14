<template>
  <banner :src="src" :alt="alt" />
  <input type="text" placeholder="Image Source" v-model="src" />
  <input type="text" placeholder="Image Alt" v-model="alt" />
</template>

<script>
import Banner from "@/components/Banner";
export default {
  name: "BannerInput",
  components: {
    Banner,
  },
  data() {
    return {
      src: "https://picsum.photos/375/125",
      alt: "Banner Image",
    };
  },
};
</script>