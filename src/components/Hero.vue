<template>
  <section
    class="relative flex flex-col items-center justify-center gap-4 md:gap-8 text-center text-white h-[643px] p-10 bg-cover bg-center"
    :style="{ backgroundImage: `url(${bg_image})` }">

    <img v-if="shapes.shape_1" :src="shapes.shape_1" alt="hero background shape left" class="absolute left-0 bottom-0 h-28 md:h-40 lg:h-82.8 lg:w-110.8" />
    <img v-if="shapes.shape_2" :src="shapes.shape_2" alt="hero background shape right" class="absolute right-0 top-0 h-28 md:h-40 lg:h-82.8 lg:w-110.8" />

    <h1 class="text-5xl md:text-[64px] font-bold">{{ heroTitle }}</h1>
    <p class="mt-4 max-w-xl">{{ subtitle }}</p>
    <ButtonCta size="xxl" :color="isFirstAccess ? 'secondary' : 'black'">
      {{ buttonLabel }}</ButtonCta>
  </section>
</template>

<script>
import ButtonCta from "./ButtonCta.vue";
export default {
  components: {
    ButtonCta,
  },
  props: {
    title: {
      type: Object,
      default: () => ({
        first_time_accessing: "",
        second_time_accessing: "",
      }),
    },
    subtitle: {
      type: String,
      default: "",
    },
    button_label: {
      type: Object,
      default: () => ({
        first_time_accessing: "",
        second_time_accessing: "",
      }),
    },
    button_link: {
      type: String,
      default: "",
    },
    bg_image: {
      type: String,
      default: "",
    },
    shapes: {
      type: Object,
      default: () => ({
        shape_1: "",
        shape_2: "",
      }),
    },
  },
  data() {
    return {
      isFirstAccess: true,
    };
  },
  computed: {
    heroTitle() {
      return this.isFirstAccess ? this.title.first_time_accessing : this.title.second_time_accessing;
    },
    buttonLabel() {
      return this.isFirstAccess ? this.button_label.first_time_accessing : this.button_label.second_time_accessing;
    },
  },
  created() {
    this.checkUserAccess();
  },
  methods: {
    checkUserAccess() {
      if (localStorage.getItem('isFirstAccess')) {
        this.isFirstAccess = false;
      } else {
        localStorage.setItem('isFirstAccess', 'false');
      }
    },
  }
};
</script>
