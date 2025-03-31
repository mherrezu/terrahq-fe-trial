<template>
  <header class="h-20 md:h-[100px] bg-light border-b">
    <nav class="flex items-center justify-between px-4 sm:px-0 py-5 md:py-6.5 sm:mx-[45px]">
      <div class="h-10 md:h-12 w-fit">
        <img :src="logo" alt="logo-terra" class="h-full w-full object-cover" />
      </div>

      <ButtonCta @click="handleMenu" color="white" size="sm" aria-label="menu button"
        class="block sm:hidden">
        <svg v-if="!menuIsOpen" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" width="24" height="24" stroke-width="2"> <path d="M10 6h10"></path> <path d="M4 12h16"></path> <path d="M7 12h13"></path> <path d="M4 18h10"></path> </svg> 
        <svg v-if="menuIsOpen" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" width="24" height="24" stroke-width="2"> <path d="M18 6l-12 12"></path> <path d="M6 6l12 12"></path> </svg>      
      </ButtonCta>

      <!-- Desktop/tablet menu -->
      <ul class="hidden sm:flex gap-8 lg:mr-[131px]">
        <li v-for="(item, key) in menu" :key="`header-links-${key}`" 
          class="cursor-pointer hover:text-secondary-500 px-6 py-4 sm:p-0">
          {{ item }}
        </li>
      </ul>

      <!-- Mobile menu -->
      <transition 
        enter-active-class="transition-opacity transition-transform duration-500 ease-out" 
        enter-from-class="opacity-0 -translate-y-5" 
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition-opacity transition-transform duration-500 ease-in" 
        leave-from-class="opacity-100 translate-y-0" 
        leave-to-class="opacity-0 -translate-y-5"
      >
        <ul v-show="menuIsOpen" 
          class="absolute z-20 top-20 left-0 flex flex-col items-center w-full h-screen bg-light sm:hidden">
          <li v-for="(item, key) in menu" :key="`header-links-mobile-${key}`" 
            class="cursor-pointer hover:text-secondary-500 px-6 py-4 sm:p-0">
            {{ item }}
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script>
import ButtonCta from './ButtonCta.vue';
export default {
  components: {
    ButtonCta
  },
  props: {
    logo: {
      type: String,
      default: ''
    },
    menu: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      menuIsOpen: false
    };
  },
  methods: {
    handleMenu() {
      this.menuIsOpen = !this.menuIsOpen;
    }
  }
};
</script>
