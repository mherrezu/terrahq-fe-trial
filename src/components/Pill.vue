<template>
  <div class=" text-light font-bold text-xs lg:text-sm" :class="{
    'absolute top-4 right-4 px-3 py-2 rounded-full': pillPosition === 'top-right',
    'absolute top-4 left-4 px-3 py-2 rounded-full': pillPosition === 'top-left',
    'absolute bottom-4 left-4 px-3 py-2 rounded-full': pillPosition === 'bottom-left',
    'absolute bottom-4 right-4 px-3 py-2 rounded-full': pillPosition === 'bottom-right',
    'bg-secondary-500': pillType === 'Type A',
    'bg-pink': pillType === 'Type B',
  }">
    <span class="">{{ label }}</span>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: "",
    },
    pillPosition: {
      type: String,
      default: "top-right",
    },
    pillType: {
      type: String,
      default: "Type A",
    },
  },
}
</script>

<style lang="scss" scoped>

</style>