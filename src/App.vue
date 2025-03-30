<template>
  <main v-if="landingComponents" class="min-h-screen">
    <template v-for="(component, index) in landingComponents" :key="index">
      <section v-if="component">
        <component :is="component.component" v-bind="component.props"></component>
      </section>
    </template>
  </main>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Intro_card from "./components/Intro_Card.vue";
import Blog from "./components/Blog.vue";
import Timeline from "./components/Timeline.vue";
import Cta from "./components/Cta.vue";
export default {
  components: {
    Navbar,
    Hero,
    Intro_card,
    Blog,
    Timeline,
    Cta,
  },
  data() {
    return {
      landingComponents: [],
    };
  },
  async created() {
    await this.fetchData();
  },
  methods: {
    async fetchData() {
      try {
        const response = await fetch("https://tf-frontend.netlify.app/trial");
        const data = await response.json();
        const components = Object.entries(data).map(([key, value]) => {
          const componentName = key.replace(/-/g, '');
          const componentProps = value || {};
          return {
            component: componentName,
            props: componentProps,
          };
        });
        this.landingComponents = components;
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    },
  },
};
</script>

