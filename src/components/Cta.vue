<template>
  <section class="px-8 sm:px-14 md:px-24 lg:px-29 pb-15">
    <div class="flex flex-col sm:flex-row items-center justify-between w-full h-full sm:h-72 lg:h-118.2 bg-olive-50">
      <div class="sm:w-1/2 h-full text-primary-950 flex flex-col justify-center items-center gap-4 md:gap-6 p-6 lg:px-20">
        <h2 class="text-2xl lg:text-[40px] font-bold ">{{ title }}</h2>
        <p class="">{{ subtitle }}</p>
      </div>
      <div class="sm:w-1/2 grid grid-cols-2 grid-rows-2 w-full h-full relative">
        <div class=""></div>
        <img :src="image_2" alt="Image 2" class="object-cover w-full h-full" />
        <img :src="image_1" alt="Image 1" class="object-cover w-full h-full" />
        <Pill :label="pill" pillPosition="bottom-right" />
    </div>
    </div>
  </section>
</template>

<script>
import Pill from "./Pill.vue";
export default {
  components: {
    Pill,
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
      pill: {
          type: String,
          default: "",
      },
      image_1: {
          type: String,
          default: "",
      },
      image_2: {
          type: String,
          default: "",
      },
  },
};
</script>
