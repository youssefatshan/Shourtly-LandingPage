<template>
  <div>
    <header class="flex justify-between items-center p-5 bg-white">
      <div class="flex items-center space-x-8 ml-0 md:ml-28">
        <img src="@/assets/logo.svg" alt="Shortly Logo" class="h-8" />
        <nav class="hidden md:flex space-x-8">
          <ul class="flex space-x-8">
            <li><a href="#" class="text-grayishViolet font-bold hover:text-veryDarkViolet">Features</a></li>
            <li><a href="#" class="text-grayishViolet font-bold hover:text-veryDarkViolet">Pricing</a></li>
            <li><a href="#" class="text-grayishViolet font-bold hover:text-veryDarkViolet">Resources</a></li>
          </ul>
        </nav>
      </div>
      <div class="hidden md:flex space-x-4 mr-20">
        <button class="text-grayishViolet font-bold hover:text-veryDarkViolet">Login</button>
        <button class="bg-cyan text-white px-6 py-2 font-bold rounded-full hover:opacity-75">Sign Up</button>
      </div>
      <button @click="toggleMenu" class="md:hidden text-grayishViolet">
        <Bars3CenterLeftIcon class="h-6 w-6" />
      </button>
    </header>
    <div v-if="menuOpen" class="absolute top-0 left-0 w-full h-screen bg-darkViolet bg-opacity-90 flex flex-col items-center justify-center text-center space-y-6 md:hidden">
      <button @click="toggleMenu" class="absolute top-5 right-5 text-gray-300">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
      <ul class="space-y-6">
        <li><a href="#" class="text-white font-bold text-lg">Features</a></li>
        <li><a href="#" class="text-white font-bold text-lg">Pricing</a></li>
        <li><a href="#" class="text-white font-bold text-lg">Resources</a></li>
      </ul>
      <hr class="border-gray-500 w-1/2">
      <button class="text-white font-bold text-lg">Login</button>
      <button class="bg-cyan text-white px-6 py-2 font-bold rounded-full">Sign Up</button>
    </div>
  </div>
</template>

<script>
import { Bars3CenterLeftIcon } from '@heroicons/vue/24/solid';

export default {
  name: 'Header',
  components: {
    Bars3CenterLeftIcon
  },
  data() {
    return {
      menuOpen: false
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    }
  }
};
</script>

<style scoped>
/* Add any additional styles if needed */
</style>
