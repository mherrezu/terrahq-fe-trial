<template>
  <section class="  p-14 lg:p-30 flex flex-col items-center">
    <h2 class="text-2xl lg:text-[40px] font-bold text-center mb-10 md:mb-18">{{ title }}</h2>
    <div class="mt-14">
      <div class="flex flex-col w-72 sm:w-[640px] lg:w-[1002px]">
        <div class="relative">
          <span class="absolute -top-10 transform -translate-x-1/2 text-3xl md:text-[40px] text-secondary-500 font-medium"
            :style="{ left: `${rangePosition}%` }">
            {{ rangePercentage }}%
          </span>
        </div>
        <div class="flex items-center justify-between mb-1 sm:mb-0">
          <p class="text-sm md:text-lg font-medium">{{ initial_item.label }}</p>
          <p class="text-sm md:text-lg font-medium">{{ final_item.label }}</p>
        </div>
        <div class="relative w-full">
          <div class="absolute top-2 sm:top-1 left-0 h-2.5 sm:h-3.7 bg-secondary-500 rounded-lg"
            :style="{ width: `${rangePosition}%` }"
          ></div>
          <label for="progress-range"></label>
          <input 
            type="range" 
            id="progress-range" 
            v-model="range" 
            :min="initial_item.data" 
            :max="final_item.data" 
            class="w-full appearance-none h-2.5 sm:h-[15px] bg-gray-300 accent-secondary-500 rounded-lg cursor-pointer" 
          />
        </div>
        <div class="flex justify-between leading-none mt-6">
          <p class="text-[40px] text-secondary-500 font-medium">{{ initial_item.data }}</p>
          <p class="text-[64px] font-bold">{{ final_item.data }}</p>
        </div>
      </div>
    </div>
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
        label: "Inicio",
        data: 250,
      }),
    },
    final_item: {
      type: Object,
      default: () => ({
        label: "Fin",
        data: 750,
      }),
    },
  },
  data() {
    return {
      range: Math.round(250 + (750 - 250) * 0.33),
    };
  },
  computed: {
    rangePercentage() {
      return Math.round(((this.range - this.initial_item.data) / (this.final_item.data - this.initial_item.data)) * 100);
    },
    rangePosition() {
      return ((this.range - this.initial_item.data) / (this.final_item.data - this.initial_item.data)) * 100;
    },
  },
};
</script>

<style scoped>
input[type="range"]::-webkit-slider-thumb {
  appearance: none;
  width: 40px;
  height: 40px;
  background-color: #189B5C;
  border-radius: 50%;
  cursor: pointer;
}

input[type="range"]::-moz-range-thumb {
  width: 40px;
  height: 40px;
  background-color: #189B5C;
  border-radius: 50%;
  cursor: pointer;
}
</style>