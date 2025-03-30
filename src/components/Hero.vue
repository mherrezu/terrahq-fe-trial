<template>
  <section class="container mx-auto  p-10">
    <p>HERO</p>
      <p>{{ title }}</p>
      <p>{{ subtitle }}</p>
      <p>{{ button_label }}</p>
      <p>{{ button_link }}</p>
      <p>{{ bg_image }}</p>
      <p>{{ shapes.shape_1 }}</p>
      <p>{{ shapes.shape_2 }}</p>
  </section>
</template>

<script>
export default {
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
};
</script>
