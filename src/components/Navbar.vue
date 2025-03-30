<template>
    <section class="container mx-auto  p-10">
    <p>NAVBAR</p>
      <p>{{ logo }}</p>
      <p>{{ menu }}</p>
  </section>
  </template>
  
  <script>
  export default {
    props: {
      logo: {
        type: String,
        default: ''
      },
      menu: {
        type: Object,
        default: () => {}
      }
    },
  };
  </script>
  