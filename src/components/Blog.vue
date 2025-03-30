<template>
    <section class="container mx-auto p-10">
      <p>BLOG</p>
      <p>{{ title }}</p>
      <p>{{ posts }}</p>
      <p>{{ button_label }}</p>
      <p>{{ button_link }}</p>
    </section>
  </template>
  
  <script>
  export default {
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
  