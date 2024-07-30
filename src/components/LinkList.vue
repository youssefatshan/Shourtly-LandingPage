<template>
  <div class="space-y-4">
    <div
      v-for="(link, index) in links"
      :key="index"
      class="bg-white flex flex-col md:flex-row items-center justify-between px-4 py-2 rounded-lg"
    >
      <a
        :href="link"
        target="_blank"
        class="text-veryDarkViolet mb-4 md:mb-0"
      >
        {{ link }}
      </a>
      <button
        @click="copyLink(link, index)"
        :class="{
          'bg-cyan': copiedIndex !== index,
          'bg-darkViolet': copiedIndex === index,
        }"
        class="text-white px-8 py-2 rounded-lg font-bold hover:opacity-75 w-full md:w-auto"
      >
        {{ copiedIndex === index ? 'Copied!' : 'Copy' }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['links'],
  data() {
    return {
      copiedIndex: null
    }
  },
  methods: {
    copyLink(link, index) {
      navigator.clipboard.writeText(link);
      this.copiedIndex = index;
      setTimeout(() => {
        this.copiedIndex = null;
      }, 3000); // Reset the state after 3 seconds
    }
  }
}
</script>

<style scoped>
/* Tailwind classes used directly in the template */
/* No additional styles needed */
</style>
