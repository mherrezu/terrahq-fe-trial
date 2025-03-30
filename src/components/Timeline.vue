<template>
    <section class="container mx-auto  p-10">
    <p>TIMELINE</p>
      <p>{{ title }}</p>
      <p>{{ initial_item }}</p>
      <p>{{ final_item }}</p>
      <p>{{ percentage }}</p>
  </section>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        default: "",
      },
      initial_item: {
        type: Object,
        default: () => ({
          label: "",
          data: "",
        }),
      },
      final_item: {
        type: Object,
        default: () => ({
          label: "",
          data: "",
        }),
      },
      percentage: {
        type: String,
        default: "",
      },
    },
  };
  </script>
  