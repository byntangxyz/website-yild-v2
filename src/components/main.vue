<script setup>
import blog from "./blog.vue";
</script>

<template>
  <main class="pt-36 min-h-screen" id="home">
    <div class="container mx-auto p-4">
      <div class="text-center">
        <h1 class="font-bold text-xl md:text-2xl lg:text-4xl mb-12">
          Selamat Datang di Website Yayasan Isyfa Lana Dhuafa
        </h1>
      </div>

      <!-- 2 Kolom -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
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
    </div>
    <blog />
  </main>

  <hr class="my-12 h-0.5 border-t-0 bg-neutral-100 dark:bg-white/10" />
</template>

<script>
export default {
  data() {
    return {
      images: [
        "/santunan-1.jpeg",
        "https://via.placeholder.com/400x300?text=Gambar+2",
        "https://via.placeholder.com/400x300?text=Gambar+3",
      ],
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
