<template>
  <div class="container mx-auto bg-lightgray px-4 md:px-12">
    <div class="bg-darkViolet text-white rounded-lg shadow-md p-6 md:p-12 relative md:-top-16 z-10 mb-16 md:mb-0">
      <div class="flex flex-col md:flex-row items-center mb-4 space-y-4 md:space-y-0 md:space-x-4">
        <input
          type="text"
          v-model="link"
          placeholder="Shorten a link here..."
          class="flex-1 px-8 py-4 rounded-lg text-black w-full"
        />
        <button
          @click="addLink"
          class="bg-cyan text-white px-8 py-4 rounded-lg w-full md:w-auto w-full font-bold hover:opacity-75"
        >
          Shorten It!
        </button>
      </div>
      <p v-if="error" class="text-red italic">{{ error }}</p>
    </div>
    <div class="mt-6 p-6 rounded-lg">
      <LinkList :links="links" />
    </div>
  </div>
</template>

<script>
import LinkList from './LinkList.vue';

export default {
  components: {
    LinkList
  },
  data() {
    return {
      link: '',
      error: '',
      links: []
    }
  },
  methods: {
    addLink() {
      if (!this.link) {
        this.error = 'Please add a link';
      } else {
        this.links.push(this.link);
        this.link = '';
        this.error = '';
      }
    }
  }
}
</script>

<style scoped>
.container {
  max-width: 900px;
}
</style>
