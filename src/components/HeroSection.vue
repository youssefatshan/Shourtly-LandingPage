<template>
  <div class="flex flex-col md:flex-row h-screen md:space-x-6 mx-auto">
    <section class="flex-1 flex flex-col justify-center items-center text-center p-8">
      <div class="text-center md:text-left md:w-[440px]">
        <h1 class="text-3xl md:text-6xl font-bold mb-4">
          More than just <br class="md:hidden"> shorter links
        </h1>
        <p class="text-lg text-grayishViolet mb-8">
          Build your brand's recognition and get detailed insights on how your links are performing.
        </p>
        <button class="bg-cyan text-white px-6 py-3 rounded-full font-bold hover:opacity-75 transition-all duration-300">Get Started</button>
      </div>
    </section>
    <section class="flex-1 flex flex-col justify-center items-center p-8 order-first md:order-none">
      <img src="@/assets/illustration-working.svg" alt="Working Illustration" class="max-w-full h-auto">
    </section>
  </div>
</template>

<style scoped>
/* Mobile Responsive */
@media (max-width: 375px) {
  h1 {
    font-size: 1.75rem;
    line-height: 1.2;
  }
  p {
    font-size: 1rem;
    line-height: 1.5;
  }
  img {
    order: -1;
  }
}
</style>
