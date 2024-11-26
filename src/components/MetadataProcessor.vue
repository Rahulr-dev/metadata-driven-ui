<template>
  <div>
    <component
      v-for="(item, index) in metadata"
      :key="index"
      :is="resolveComponent(item.type)"
      v-bind="item.props"
      :count="currentCount"
      @action="handleButtonClick(item.props, index)" 
    />
  </div>
</template>

<script>
import Heading from './Heading.vue';
import Image from './Image.vue';
import Counter from './Counter.vue';
import Button from './Button.vue';

export default {
  props: {
    metadata: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      currentCount: 0, // Initialize count for the counter component
    };
  },
  methods: {
    resolveComponent(type) {
      const components = {
        Heading,
        Image,
        Counter,
        Button
      };
      return components[type] || null;
    },
    handleIncrement(incrementValue) {
      this.currentCount += incrementValue;
      this.$emit('countUpdated', this.currentCount);
    },
    handleButtonClick(props, index) {
      const action = props.action;
      switch (action) {
        case 'increment':
          // Handle increment logic
          this.handleIncrement(1);
          break;
        case 'alert':
          // Show an alert with the message from metadata
          alert(props.message);
          break;
        default:
          console.log('Unknown action');
      }
    }
  }
};
</script>
