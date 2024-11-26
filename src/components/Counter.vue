<template>
  <div>
    <p>Current Count: {{ count }}</p>
  </div>
</template>

<script>
export default {
  props: {
    count: {
      type: Number,
      default: 0
    }
  }
};
</script>

<!-- <template>
  <div>
    <p>Current Count: {{ count }}</p>
    <button @click="incrementCount">Increment</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    };
  },
  methods: {
    incrementCount() {
      this.count++;
      this.$emit('countUpdated', this.count); // Emit updated count to parent
    }
  }
};
</script> -->
