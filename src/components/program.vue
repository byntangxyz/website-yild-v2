<template>
  <section class="pt-16 min-h-screen" id="program">
    <div class="container mx-auto p-4">
      <h2 class="text-center font-bold text-2xl mb-14 lg:text-4xl">
        Program Kami
      </h2>

      <!-- Kartu Program -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <!-- Program 1: Pembangunan Pondok Tahfidz -->
        <div
          class="bg-white rounded-lg shadow-md overflow-hidden transition-transform transform hover:scale-105"
        >
          <img
            src="/article-1.jpeg"
            alt="Pembangunan Pondok Tahfidz"
            class="w-full h-48 object-cover"
          />
          <div class="p-4">
            <h3 class="font-semibold text-lg">Pembangunan Pondok Tahfidz</h3>
            <p class="text-sm text-gray-600 mt-2">
              Program ini bertujuan untuk membangun fasilitas belajar Al-Qur'an
              bagi generasi muda yang ingin mendalami ilmu agama.
            </p>
          </div>
        </div>

        <!-- Program 2: Santunan Yatim & Piatu -->
        <div
          class="bg-white rounded-lg shadow-md overflow-hidden transition-transform transform hover:scale-105"
        >
          <img
            src="/santunan-2.jpeg"
            alt="Santunan Yatim & Piatu"
            class="w-full h-48 object-cover"
          />
          <div class="p-4">
            <h3 class="font-semibold text-lg">Santunan Yatim & Piatu</h3>
            <p class="text-sm text-gray-600 mt-2">
              Melalui program ini, yayasan memberikan dukungan finansial dan
              emosional kepada anak-anak yatim dan piatu untuk memenuhi
              kebutuhan hidup mereka.
            </p>
          </div>
        </div>

        <!-- Program 3: Pemberdayaan UMKM -->
        <div
          class="bg-white rounded-lg shadow-md overflow-hidden transition-transform transform hover:scale-105"
        >
          <img
            src="https://via.placeholder.com/400x250?text=Pemberdayaan+UMKM"
            alt="Pemberdayaan UMKM"
            class="w-full h-48 object-cover"
          />
          <div class="p-4">
            <h3 class="font-semibold text-lg">Pemberdayaan UMKM</h3>
            <p class="text-sm text-gray-600 mt-2">
              Yayasan berfokus membantu UMKM lokal dengan memberikan pelatihan
              dan pendampingan agar dapat mandiri secara ekonomi dan
              meningkatkan taraf hidup.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <hr class="my-12 h-0.5 border-t-0 bg-neutral-100 dark:bg-white/10" />
</template>

<script>
export default {
  name: "ProgramPage",
};
</script>

<style scoped>
/* Animasi hover untuk transformasi */
.transition-transform:hover {
  transform: scale(1.05);
}
</style>
