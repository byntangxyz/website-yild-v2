<template>
  <section
    class="relative w-full h-screen overflow-hidden bg-gray-900 text-white"
    id="bergabung"
  >
    <!-- Slider Background Images -->
    <div class="absolute inset-0 w-full h-full">
      <div
        v-for="(image, index) in images"
        :key="index"
        :style="{ backgroundImage: `url(${image})` }"
        class="absolute inset-0 bg-cover bg-center transition-opacity duration-1000"
        :class="{
          'opacity-0': currentImage !== index,
          'opacity-100': currentImage === index,
        }"
      ></div>
    </div>

    <!-- Konten di Atas Slider -->
    <div
      class="relative z-10 flex items-center justify-center w-full h-full bg-black bg-opacity-50 px-4"
    >
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl">
        <!-- Kolom 1: Quotes -->
        <div class="bg-white bg-opacity-20 p-6 rounded-lg shadow-md">
          <blockquote
            class="text-lg lg:text-2xl font-semibold italic text-gray-200"
          >
            “Sebaik-baik manusia adalah yang paling bermanfaat bagi orang lain.”
            <br />
            <span class="text-sm lg:text-base">— Hadis Nabi Muhammad SAW</span>
          </blockquote>
        </div>

        <!-- Kolom 2: Rekening Bank dan Tombol Bergabung -->
        <div class="bg-white bg-opacity-20 p-6 rounded-lg shadow-md">
          <h3 class="font-bold text-xl mb-4 lg:text-3xl">Rekening Bank</h3>
          <p class="text-sm text-gray-300 lg:text-lg">
            Bank Syariah Indonesia (BSI): 1234567890 a.n Yayasan Isyfa Lana
            Dhuafa
          </p>
          <p class="text-sm text-gray-300 mt-2 lg:text-lg">
            Bank Mandiri: 0987654321 a.n Yayasan Isyfa Lana Dhuafa
          </p>
          <button
            class="mt-6 bg-green-600 hover:bg-green-700 text-white py-2 px-4 rounded-lg transition text-lg"
            @click="handleJoin"
          >
            Donasi
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      images: ["/qurban-2023.jpeg", "/pengajian-1.jpeg", "/santunan-3.jpeg"],
      currentImage: 0,
    };
  },
  mounted() {
    this.startImageSlider();
  },
  methods: {
    startImageSlider() {
      setInterval(() => {
        this.currentImage = (this.currentImage + 1) % this.images.length;
      }, 5000); // Ganti gambar setiap 5 detik
    },
    handleJoin() {
      alert("Terima kasih telah bergabung bersama kami!");
    },
  },
};
</script>

<style scoped>
/* Mengatur transisi antar gambar */
.opacity-0 {
  opacity: 0;
}
.opacity-100 {
  opacity: 1;
}
</style>
