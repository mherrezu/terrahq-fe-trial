<template>
  <section class="flex flex-col items-center justify-center gap-8 lg:gap-18 bg-olive-50 px-8 pb-8 sm:px-14 sm:pb-14 lg:px-30 lg:pb-30">
    <h2 class="text-2xl lg:text-[40px] text-center font-bold">{{ title }}</h2>
    <ul class="grid grid-cols-12 gap-4 lg:gap-8 w-full">
      <li v-for="(post, index) in posts" :key="`blog-card-${index}`" 
          class=" col-span-12 sm:col-span-6 lg:col-span-3 flex flex-col h-full w-full">
        <ImgWithPill 
          :image="post.image" 
          imgHeight="90.5" 
          imgWidth="full" 
          :pill="post.type" 
          :pillType="post.type" 
          pillPosition="top-left" 
          class="mb-4"/>
        <p class="text-sm font-bold">{{ post.date }}</p>
        <h3 class="mt-1 mb-6">{{ post.title }}</h3>
      </li>
    </ul>
    <ButtonCta size="xxl" color="secondary">{{ button_label }}</ButtonCta>
  </section>
</template>

<script>
import ButtonCta from "./ButtonCta.vue";
import ImgWithPill from "./ImgWithPill.vue";
export default {
  components: {
    ButtonCta,
    ImgWithPill,
  },
  props: {
    title: {
      type: String,
      default: "",
    },
    posts: {
      type: Object,
      default: () => ({}),
    },
    button_label: {
      type: String,
      default: "",
    },
    button_link: {
      type: String,
      default: "",
    },
  },
};
</script>
