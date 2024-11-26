<template>
  <div>
    <h2>Metadata-Driven UI Demo</h2>
    <button @click="loadExample(1)">Load Example 1</button>
    <button @click="loadExample(2)">Load Example 2</button>
    <MetadataProcessor :metadata="metadata" @countUpdated="updateCount" />
    <p>Count in Parent Component: {{ sharedCount }}</p>
  </div>
</template>

<script>
import MetadataProcessor from './components/MetadataProcessor.vue';
import axios from 'axios';

export default {
  components: { MetadataProcessor },
  data() {
    return {
      metadata: [], // Reactive metadata array
      sharedCount: 0
    };
  },
  methods: {
    async loadExample(exampleNumber) {
      try {
        const response = await axios.get(`/example-metadata${exampleNumber}.json`);
        this.metadata = response.data; // Update metadata
      } catch (error) {
        console.error('Failed to fetch metadata:', error);
      }
    },
    updateCount(newCount) {
      this.sharedCount = newCount; // Update shared count when event is received
    },
  }
};
</script>
