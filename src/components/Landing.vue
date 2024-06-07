<template>
  <section id="landing" class="relative">
    <div class="flex justify-center mt-48 mb-64 md:my-64 md:items-center">
      <div
        class="dark:text-gray-200 text-gray-900 text-center max-w-screen-md mx-auto relative z-30"
      >
        <div class="flex justify-center mb-8">
          <div class="relative">
            <img
              class="rounded-full border-2 animated-circle-outline w-32 relative z-20"
              alt="me"
              src="../assets/self-image.jpg"
            />
          </div>
        </div>
        <h1
          class="text-3xl md:text-5xl font-bold mb-4 dark:text-slate-200 text-slate-700"
        >
          Front-end Engineer & UX Designer
        </h1>
        <p class="mb-8 lg:mb-10 font-light text-center text-gray-500 dark:text-gray-400 sm:text-xl">
          Take a moment to explore my portfolio to see some of my past projects.
          Please feel free to reach out if you’d like to learn more.
        </p>
        <button
          class="text-white rounded-full py-2 bg-transparent px-6 transition duration-500 hover:shadow-lg hover:shadow-emerald-500/20 bg-emerald-500 dark:bg-transparent dark:border dark:border-emerald-400"
          @click="toggleWorkPage"
        >
          Explore my work
        </button>
      </div>
    </div>
  </section>
</template>

<script>

export default {
    methods: {
        toggleWorkPage() {
            this.$emit("toggle-work-page");
        },
    },
};
</script>

<style lang="scss" scoped></style>
