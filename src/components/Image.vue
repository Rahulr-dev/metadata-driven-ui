<template>
  <img :src="src" :alt="alt" :style="style"/>
</template>

<script>
export default {
  // mounted() {
  //   // Load default dataset
  //   console.log("called", style)
  // },
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    },
    style: {
      type: Object,
      default: () => ({}), // Default to an empty object if no style is provided
    },
  }
};
</script>
