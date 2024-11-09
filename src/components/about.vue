<template>
  <section class="pt-28 bg-slate-500 min-h-screen" id="tentang">
    <div class="container mx-auto p-4">
      <h2 class="text-center font-bold text-4xl mb-8 text-white">
        Tentang Kami
      </h2>

      <!-- 3 Kolom -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <!-- Kolom Slider Pengurus Yayasan -->
        <div class="flex flex-col items-center">
          <div
            class="relative w-48 h-48 overflow-hidden rounded-full shadow-lg mb-4"
          >
            <img
              :src="pengurus[currentPengurusIndex].foto"
              alt="Pengurus"
              class="w-full h-full object-cover transition-opacity duration-1000"
            />
          </div>
          <h3 class="text-lg font-semibold text-white md:text-xl lg:2xl">
            {{ pengurus[currentPengurusIndex].nama }}
          </h3>
          <p class="text-sm text-gray-300 md:text-base lg:text-lg">
            {{ pengurus[currentPengurusIndex].jabatan }}
          </p>
        </div>

        <!-- Kolom Visi -->
        <div
          class="flex flex-col items-center text-center p-4 bg-white rounded-lg shadow-md"
        >
          <div class="text-4xl mb-2">
            <i class="ph ph-eye"></i>
          </div>
          <h3 class="font-semibold text-lg mb-2">Visi</h3>
          <p class="text-sm text-gray-600">
            Menjadi lembaga yang bermanfaat bagi masyarakat dan lingkungan.
          </p>
        </div>

        <!-- Kolom Misi -->
        <div
          class="flex flex-col items-center text-center p-4 bg-white rounded-lg shadow-md"
        >
          <div class="text-4xl mb-2">
            <i class="ph ph-target"></i>
          </div>
          <h3 class="font-semibold text-lg mb-2">Misi</h3>
          <ul
            class="text-sm text-gray-600 space-y-2 list-inside list-disc text-left"
          >
            <li>Turut serta dalam program pemberdayaan sosial.</li>
            <li>
              Berperan aktif dalam membina, melatih dan memberikan keterampilan.
            </li>
            <li>
              Berperan aktif menghimpun dan menyalurkan zakat, infaq dan
              shodaqoh.
            </li>
            <li>
              Menghimpun, mengembangkan dan mengelola tanah wakaf baik yang
              berupa barang bergerak (uang) maupun tidak bergerak (tanah).
            </li>
            <li>
              Sebagai mitra program pengembangan Usaha Kesejahteraan Sosial (UKS).
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <hr class="my-12 h-0.5 border-t-0 bg-neutral-100 dark:bg-white/10" />
</template>

<script>
export default {
  data() {
    return {
      pengurus: [
        {
          foto: "https://via.placeholder.com/150?text=Foto+1",
          nama: "Budi Santoso",
          jabatan: "Ketua Yayasan",
        },
        {
          foto: "https://via.placeholder.com/150?text=Foto+2",
          nama: "Siti Aminah",
          jabatan: "Bendahara",
        },
        {
          foto: "https://via.placeholder.com/150?text=Foto+3",
          nama: "Rahmat Hidayat",
          jabatan: "Sekretaris",
        },
      ],
      currentPengurusIndex: 0,
    };
  },
  mounted() {
    this.startPengurusSlider();
  },
  methods: {
    startPengurusSlider() {
      setInterval(() => {
        this.currentPengurusIndex =
          (this.currentPengurusIndex + 1) % this.pengurus.length;
      }, 5000); // Ganti pengurus setiap 3 detik
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
