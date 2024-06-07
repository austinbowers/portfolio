<template class="relative">
  <div class="relative overflow-hidden min-h-screen">
    <Header />
    <section class="z-30 px-8" v-if="!workPage">
      <Landing @toggle-work-page="toggleWorkPage" />
      <FreelanceWebDesign class="hidden"></FreelanceWebDesign>
      <ContactForm></ContactForm>
    </section>
    <section class="z-30" v-if="workPage">
      <div
        class="px-8 dark:text-gray-200 text-gray-900 mx-auto max-w-screen-lg relative mt-24 z-30"
      >
        <p @click="toggleWorkPage" class="cursor-pointer text-green-400 mb-8 inline-flex items-center gap-2">
          <svg class="rotate-180" xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
            <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708"/>
          </svg>
          Back to home
        </p>
        <div
          class="dark:text-gray-200 text-gray-900 text-center max-w-screen-lg relative z-30"
        >
          <div class="grid grid-cols-2 lg:grid-cols-3 gap-4 md:gap-6 lg:gap-10">
            <ImageSquare url="src/assets/photos/Back.jpg"></ImageSquare>
            <ImageSquare url="src/assets/photos/Back2.jpg"></ImageSquare>
            <ImageSquare url="src/assets/photos/BHBWavy.png"></ImageSquare>
            <ImageSquare url="src/assets/photos/BHB_Funky_Letters.png"></ImageSquare>
            <ImageSquare url="src/assets/photos/planetrotating.gif"></ImageSquare>
            <ImageSquare url="src/assets/photos/THE_ONE.png"></ImageSquare>
            <ImageSquare url="src/assets/photos/jimwall.jpg"></ImageSquare>
            <ImageSquare url="src/assets/photos/Lennon.jpg"></ImageSquare>
            <ImageSquare url="src/assets/photos/JerryGarcia_Small.jpg"></ImageSquare>
            <ImageSquare url="src/assets/photos/FrankSinatra.jpg"></ImageSquare>
          </div>
        </div>
        <ContactForm></ContactForm>
      </div>
    </section>
    <footer>
      <div class="mt-48 mb-16 w-full bg-gradient from-emerald-300 to-emerald-900 dark:text-slate-600 px-6" id="footer">
        <p><small><center>© {{ new Date().getFullYear() }} Austin Bowers </center></small></p>
        <p><small><center>Website Designed and Developed by Austin Bowers</center></small></p>
    </div>
    </footer>
    <div
      class="animated-blur-1 absolute rounded-full blur-2xl dark:bg-emerald-500 bg-emerald-500 top-0 z-20"
    ></div>
    <div
      class="animated-blur-2 absolute rounded-full blur-2xl dark:bg-blue-500 bg-blue-500 top-0 z-10"
    ></div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Landing from "./components/Landing.vue";
import LowerLeftNav from "./components/LowerLeftNav.vue";
import FreelanceWebDesign from "./components/FreelanceWebDesign.vue";
import ImageSquare from "./components/ImageSquare.vue";
import ContactForm from "./components/ContactForm.vue";

export default {
  components: {
    Header,
    Landing,
    LowerLeftNav,
    FreelanceWebDesign,
    ImageSquare,
    ContactForm
},
  data() {
    return {
      workPage: false,
    };
  },
  methods: {
    toggleWorkPage() {
      this.workPage = !this.workPage;
    },
  },
};
</script>

<style lang="scss">
body {
  @apply transition duration-300;
}
.animated-circle-outline {
  @apply border-emerald-400;
  animation: 6s linear infinite alternate ease-in-out;
  animation-name: circle-outline-color-change;
}
.animated-blur-1 {
  animation: 35s linear infinite alternate ease-in-out;
  animation-name: blur-move-1;
  opacity: 0;
}
.animated-blur-2 {
  animation: 35s linear infinite alternate ease-in-out;
  animation-name: blur-move-2;
  opacity: 0;
}

@keyframes circle-outline-color-change {
  0% {
    @apply border-emerald-400;
  }
  50% {
    @apply border-blue-400;
  }
  100% {
    @apply border-emerald-400;
  }
}

@keyframes blur-move-1 {
  0% {
    opacity: 0;
    top: 5%;
    left: 5%;
    right: 40%;
    height: 20rem;
    width: 20rem;
  }
  50% {
    opacity: 60%;
    top: 60%;
    left: 80%;
    right: 20%;
    height: 60rem;
    width: 60rem;
  }
  100% {
    opacity: 0;
    top: 5%;
    left: 5%;
    right: 40%;
    height: 20rem;
    width: 20rem;
  }
}
@keyframes blur-move-2 {
  0% {
    opacity: 0;
    top: 10%;
    left: 50%;
    right: 0%;
    height: 60rem;
    width: 60rem;
  }
  50% {
    opacity: 50%;
    top: 0%;
    right: 100%;
    left: 0%;
    height: 30rem;
    width: 30rem;
  }
  100% {
    opacity: 0;
    top: 10%;
    left: 50%;
    right: 0%;
    height: 60rem;
    width: 60rem;
  }
}
</style>
