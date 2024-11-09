<template>
  <section class="py-12">
    <div class="container mx-auto px-4">
      <h2 class="text-2xl font-bold mb-6 text-gray-800">Artikel Terbaru</h2>
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 overflow-x-auto pb-4 lg:pb-0 lg:grid-flow-row lg:auto-cols-fr lg:gap-6 mb-8"
      >
        <!-- Card untuk setiap artikel -->
        <div
          v-for="(artikel, index) in artikelList"
          :key="index"
          class="min-w-full sm:min-w-[300px] lg:min-w-0 bg-white shadow-md rounded-lg overflow-hidden flex-shrink-0 lg:flex-shrink grid-item"
        >
          <img
            :src="artikel.image"
            alt="Gambar Artikel"
            class="w-full h-40 object-cover"
          />
          <div class="p-4">
            <h3 class="font-semibold text-lg text-gray-800 truncate">
              {{ artikel.title }}
            </h3>
            <p class="text-xs text-gray-500 mb-2">{{ artikel.date }}</p>
            <p class="text-sm text-gray-600 line-clamp-3">
              {{ artikel.description }}
            </p>
          </div>
        </div>
      </div>
      <a
        href="https://yild-artikel.webflow.io/"
        target="_blank"
        class="text-center text-base lg:text-lg rounded-md bg-slate-950 text-white shadow-lg p-4"
        >Selengkapnya....</a
      >
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      artikelList: [
        {
          image:
            "https://cdn.prod.website-files.com/670ce596aca62063e545ab1b/671115614fd46c9f56fcc654_WhatsApp%20Image%202024-09-29%20at%2017.04.34%20(2).jpeg",
          title: "Sedekah Terbaik",
          date: "17 October 2024",
          description:
            "Tak seperti zakat, sedekah bisa dilakukan oleh siapa saja, termasuk mereka yang tak memiliki kemampuan materiel. Bahkan, kemungkinan sedekah dari mereka yang kurang mampu justru mendatangkan lebih banyak pahala. Mengapa? Karena itu termasuk dalam sedekah terbaik. Apa maksudnya?",
        },
        {
          image: "/zakat.webp",
          title: "Pengertian Zakat, Syarat, dan Jenisnya Lengkap Menurut Islam",
          date: "25 Oktober 2024",
          description:
            "Tahukah kamu kalau zakat masuk ke daftar ibadah wajib untuk dilakukan, sama seperti ibadah sholat dan puasa? Lantas, bagaimana kita bisa melaksanakan ibadah zakat secara kaffah? Mari kita kenalan terlebih dahulu dengan pengertian zakat, syarat, dan jenisnya lengkap menurut Islam",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Membuat tampilan scroll horizontal */
.grid {
  scroll-snap-type: x mandatory;
}
.grid-item {
  scroll-snap-align: start;
}
</style>
