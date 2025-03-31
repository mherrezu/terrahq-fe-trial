<template>
  <section class="bg-olive-50 p-8 sm:p-14 lg:p-30 flex items-center justify-center">
    <div class="flex flex-col sm:flex-row md:h-68 lg:h-108  ">
      <div class="sm:w-1/2 h-5/6 bg-light text-primary-950 flex flex-col justify-center items-center gap-4 md:gap-6 p-6 lg:px-20">
        <h2 class="text-2xl lg:text-[40px] font-bold ">{{ title }}</h2>
        <p class="">{{ subtitle }}</p>
      </div>
      <ImgWithPill :image="image" imgHeight="full" imgWidth="full" :pill="pill" pillPosition="top-right" class="sm:w-1/2" />
    </div>
  </section>
</template>
  
<script>
import ImgWithPill from "./ImgWithPill.vue";
export default {
  components: {
    ImgWithPill,
  },
  props: {
    title: {
      type: String,
      default: "",
    },
    subtitle: {
      type: String,
      default: "",
    },
    image: {
      type: String,
      default: "",
    },
    pill: {
      type: String,
      default: "",
    },
  },
};
</script>
