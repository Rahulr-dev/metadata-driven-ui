<template>
  <div>
    <button @click="handleClick" :style="style">{{ label }}</button>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      required: true
    },
    action: {
      type: String,
      required: true
    },
    style: {
      type: Object,
      default: () => ({}), // Default to an empty object if no style is provided
    },
  },
  methods: {
    handleClick() {
      // Emit the action directly (e.g., increment or alert)
      this.$emit('action', this.action); 
    }
  }
};
</script>
