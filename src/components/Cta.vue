<template>
    <section class="container mx-auto  p-10">
    <p>CTA</p>
      <p>{{ title }}</p>
      <p>{{ subtitle }}</p>
      <p>{{ pill }}</p>
      <p>{{ image_1 }}</p>
      <p>{{ image_2 }}</p>
  </section>
  </template>
  
  <script>
  export default {
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
  