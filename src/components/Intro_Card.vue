<template>
  <section class="container mx-auto  p-10">
    <p>INTRO CARD</p>
      <p>{{ title }}</p>
      <p>{{ subtitle }}</p>
      <p>{{ image }}</p>
      <p>{{ pill }}</p>
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
  