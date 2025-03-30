<template>
  <button type="button" class="flex items-center justify-center cursor-pointer transition-all duration-500 ease-in-out"
    :disabled="disabled" :class="buttonClasses" @click="handleClick">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: "primary",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: "md",
    }
  },
  computed: {
    buttonClasses() {
      return {
        "px-3.5 py-2 gap-x-2 text-sm": this.size === "sm",
        "px-4 py-2.5 gap-x-2 text-sm": this.size === "md",
        "px-4 py-2 gap-x-2 text-md": this.size === "lg",
        "px-5 py-3 gap-x-2 text-md": this.size === "xl",
        "px-10 py-4 gap-x-3 text-md": this.size === "xxl",

        "bg-primary-950 hover:bg-primary-800 focus:bg-primary-700 text-white hover:text-black focus:text-white":
          this.color === "primary" && !this.disabled,
        "cursor-not-allowed border border-primary-200 text-primary-400 stroke-current":
          this.color === "primary" && this.disabled,

        "bg-secondary-500 hover:bg-secondary-800 focus:bg-secondary-400 text-white hover:text-secondary-400":
          this.color === "secondary" && !this.disabled,
        "cursor-not-allowed bg-secondary-50 text-secondary-500 stroke-current":
          this.color === "secondary" && this.disabled,

        "bg-black hover:bg-primary-400 focus:bg-primary-800 text-white hover:text-black focus:text-white":
          this.color === "black" && !this.disabled,
        "cursor-not-allowed border border-primary-200 text-primary-400 stroke-current":
          this.color === "black" && this.disabled,

      };
    }
  },
  methods: {
    handleClick($ev) {
      if (this.disabled) {
        $ev.stopPropagation();
      }
    },
  },
};
</script>