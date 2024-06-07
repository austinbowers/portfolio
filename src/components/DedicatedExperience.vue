<template>
    <div>
          <div class="py-24 md:py-64 px-8 md:px-4 max-w-screen-md mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-3 mb-4">
              <div class="md:col-span-2">
                <h3
                  class="text-xl md:text-3xl font-bold mb-2 dark:text-slate-200 text-slate-700"
                >
                  Demonstrated dedicated <span class="text-emerald-400">experience</span>
                </h3>
                <p class="font-light mb-5 text-slate-600 dark:text-slate-400">
                  working with front-end builds and designs, including:
                </p>
              </div>
            </div>
            <div class="flex flex-wrap items-center gap-4 mb-4">
              <div
                class="cursor-pointer text-emerald-500 rounded-full py-1 text-sm inline-flex bg-transparent font-medium px-6 transition duration-500 hover:shadow-lg dark:hover:shadow-emerald-500/20 hover:shadow-emerald-500/20 border border-emerald-500"
                @click="toggleWorkPage"
              >
                # Admin Dashboards
              </div>
              <div
                class="cursor-pointer text-emerald-400 rounded-full py-1 text-sm inline-flex bg-transparent font-medium px-6 transition duration-500 hover:shadow-lg dark:hover:shadow-emerald-500/20 hover:shadow-emerald-500/20 border border-emerald-400"
                @click="toggleWorkPage"
              >
                # Branded Web Pages
              </div>
              <div
                class="cursor-pointer text-emerald-300 rounded-full py-1 text-sm inline-flex bg-transparent font-medium px-6 transition duration-500 hover:shadow-lg dark:hover:shadow-emerald-500/20 hover:shadow-emerald-500/20 border border-emerald-300"
                @click="toggleWorkPage"
              >
                # Logo Design
              </div>
              <div
                class="cursor-pointer text-emerald-200 rounded-full py-1 text-sm inline-flex bg-transparent font-medium px-6 transition duration-500 hover:shadow-lg dark:hover:shadow-emerald-500/20 hover:shadow-emerald-500/20 border border-emerald-200"
                @click="toggleWorkPage"
              >
                # Blog Graphics
              </div>
            </div>
          </div>
        </div>
</template>

<script>
export default {
    setup () {
        

        return {}
    }
}
</script>

<style lang="scss" scoped>

</style>