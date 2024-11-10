<script setup>
import blog from "./blog.vue";
import { ref } from "vue";

const isMenuLink = ref(false);
</script>

<template>
  <main class="pt-24 min-h-screen" id="home">
    <div class="container mx-auto p-4">
      <div class="text-center">
        <h1 class="font-bold text-xl md:text-2xl lg:text-4xl mb-6">
          Selamat Datang di Website Yayasan Isyfa Lana Dhuafa
        </h1>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center mb-6">
        <!-- Kolom Slider Gambar -->
        <div>
          <div
            class="relative w-full h-64 overflow-hidden rounded-lg shadow-lg"
          >
            <img
              :src="images[currentImageIndex]"
              alt="Slider Image"
              class="w-full h-full object-cover transition-opacity duration-1000"
            />
          </div>
        </div>

        <!-- Kolom Informasi Yayasan -->
        <div class="text-left space-y-4">
          <h2 class="font-semibold text-lg md:text-xl lg:text-2xl">
            Bersama Kami,
          </h2>
          <p class="text-sm text-gray-600 md:text-base lg:text-lg">
            Yayasan Isyfa Lana Dhuafa merupakan lembaga yang bergerak dibidang
            sosial, pendidikan, dan pemberdayaan UMKM.
          </p>
          <p class="text-sm text-gray-600 md:text-base lg:text-lg">
            Kami mengundang Anda untuk bergabung dalam berbagai program dan
            kegiatan sosial yang kami selenggarakan untuk bersama-sama
            memberikan manfaat bagi masyarakat.
          </p>
        </div>
      </div>
      <div
        class="bg-slate-300 max-w-52 h-8 text-center pt-1 border-black border hover:bg-slate-200 mx-auto lg:hidden"
      >
        <a
          class="text-center p-4 font-semibold text-base"
          @click="isMenuLink = !isMenuLink"
          >Tautan Cepat <i class="ph ph-caret-down font-semibold"></i
        ></a>
      </div>
      <div ref="link" class="" :class="{ hidden: !isMenuLink }">
        <ul class="">
          <li
            class="group block border-x border-black max-w-52 text-center mx-auto pt-1 mt-0 hover:bg-slate-100"
          >
            <a href="https://arsip.yayasanisyfalanadhufa.org/" class="text-base text-black group-hover:text-primary"
              >Arsip Dokumentasi</a
            >
          </li>
          <li class="group group block border border-black max-w-52 text-center mx-auto pt-1 mt-0">
            <a href="https://yild-artikel.webflow.io/" class="text-base text-black group-hover:text-primary"
              >Laman Artikel</a
            >
          </li>
        </ul>
      </div>
    </div>
    <blog />
  </main>

  <hr class="my-12 h-0.5 border-t-0 bg-neutral-100 dark:bg-white/10" />
</template>

<script>
export default {
  data() {
    return {
      images: ["/santunan-1.jpeg", "/umkm-2.jpeg", "/qurban-2022.jpeg"],
      currentImageIndex: 0,
    };
  },
  mounted() {
    this.startSlider();
  },
  methods: {
    startSlider() {
      setInterval(() => {
        this.currentImageIndex =
          (this.currentImageIndex + 1) % this.images.length;
      }, 7000); // Ganti gambar setiap 3 detik
    },
  },
};
</script>

<style scoped>
/* Animasi fade-in */
img {
  opacity: 0;
  animation: fade-in 1s forwards;
}

@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
