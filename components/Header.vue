<script setup>
import { ref, onMounted } from "vue";

const isOpen = ref(false);
const isDesktop = ref(false);

const checkDesktop = () => {
  isDesktop.value = window.innerWidth >= 768;
  if (isDesktop.value) isOpen.value = false;
};

onMounted(() => {
  checkDesktop();
  window.addEventListener("resize", checkDesktop);
});
</script>

<template>
  <!-- Header -->
  <header
    class="bg-[url('/images/mobile/image-hero.jpg')] bg-no-repeat bg-cover bg-center h-screen px-5 md:px-[10rem] py-10"
  >
    <div class="flex justify-between items-center">
      <!-- Logo -->
      <div>
        <img src="/images/logo.svg" alt="Logo" />
      </div>

      <!-- Icon burger -->
      <div class="md:hidden">
        <button @click="isOpen = true">
          <img src="/images/icon-hamburger.svg" alt="Icon hamburger" />
        </button>
      </div>

      <!-- Navigation -->
      <nav
        v-if="isOpen || isDesktop"
        class="absolute top-0 left-0 right-0 bottom-0 h-screen bg-black text-white p-7 md:static md:block md:bg-transparent md:p-0 md:h-auto"
      >
        <!-- Icon close -->
        <div class="flex justify-between items-center md:hidden">
          <div>
            <button>
              <img src="/images/logo.svg" alt="Logo" />
            </button>
          </div>
          <div>
            <button @click="isOpen = false">
              <img src="/images/icon-close.svg" alt="Icon close" />
            </button>
          </div>
        </div>
        <!-- Link -->
        <ul
          class="flex flex-col md:flex-row md:space-x-8 space-y-4 md:space-y-0 pt-40 md:pt-0 leading-8"
        >
          <li>
            <a
              href="#"
              class="relative text-2xl md:text-lg text-white before:content-[''] before:absolute before:top-10 before:-bottom-1 before:left-0 before:h-[2px] before:w-full before:bg-white before:scale-x-0 before:origin-center before:transition-transform before:duration-300 hover:before:scale-x-100"
            >
              About
            </a>
          </li>
          <li>
            <a
              href="#"
              class="relative text-2xl md:text-lg text-white before:content-[''] before:absolute before:top-10 before:-bottom-1 before:left-0 before:h-[2px] before:w-full before:bg-white before:scale-x-0 before:origin-center before:transition-transform before:duration-300 hover:before:scale-x-100"
            >
              Careers
            </a>
          </li>
          <li>
            <a
              href="#"
              class="relative text-2xl md:text-lg text-white before:content-[''] before:absolute before:top-10 before:-bottom-1 before:left-0 before:h-[2px] before:w-full before:bg-white before:scale-x-0 before:origin-center before:transition-transform before:duration-300 hover:before:scale-x-100"
            >
              Events
            </a>
          </li>
          <li>
            <a
              href="#"
              class="relative text-2xl md:text-lg text-white before:content-[''] before:absolute before:top-10 before:-bottom-1 before:left-0 before:h-[2px] before:w-full before:bg-white before:scale-x-0 before:origin-center before:transition-transform before:duration-300 hover:before:scale-x-100"
            >
              Products
            </a>
          </li>
          <li>
            <a
              href="#"
              class="relative text-2xl md:text-lg text-white before:content-[''] before:absolute before:top-10 before:-bottom-1 before:left-0 before:h-[2px] before:w-full before:bg-white before:scale-x-0 before:origin-center before:transition-transform before:duration-300 hover:before:scale-x-100"
            >
              Support
            </a>
          </li>
        </ul>
      </nav>
    </div>
    <div
      class="flex justify-center md:justify-start mt-[12rem] border-2 border-white p-5 md:p-10 w-full md:max-w-[60%]"
    >
      <h1 class="text-[2.7rem] md:text-7xl max-w-[40rem] uppercase text-white">
        Immersive experiences that deliver
      </h1>
    </div>
  </header>
</template>
