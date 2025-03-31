<template>
  <div :class="`relative h-${imgHeight} w-${imgWidth}`">
    <Pill :label="pill" :pillPosition="pillPosition" :pillType="pillType" />
    <img :src="image" :alt="getImageAlt(image)" class="w-full h-full object-cover" />
  </div>
</template>

<script>
import Pill from "./Pill.vue";
export default {
  components: {
    Pill,
  },
  props: {
    image: {
        type: String,
        default: "",
    },
    imgHeight: {
        type: String,
        default: "h-40",
    },
    imgWidth: {
        type: String,
        default: "w-full",
    },
    pill: {
        type: String,
        default: "",
    },
    pillPosition: {
        type: String,
        default: "top-right",
    },
    pillType: {
        type: String,
        default: "Type A",
    },
  },
  methods: {
    getImageAlt(url) {
      for (var i = url.length - 1; i >= 0; i--) {
      if (url[i] === '.') {
          var substring = '';
          for (var j = i - 1; j >= 0; j--) {
              if (url[j] === '/') {
                  return substring;
              }
              substring = url[j] + substring;
          }
          return substring;
      }
    }
      return 'image';
    },
  }
}
</script>