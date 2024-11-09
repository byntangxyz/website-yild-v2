<template>
  <!-- Wrapper utama yang menutupi seluruh layar -->
  <div
    class="relative min-h-screen bg-cover bg-center flex items-center justify-center mt-16 lg:mt-20 w3-animate-opacity"
    :style="{ backgroundImage: `url('/bg.jpg')` }"
  >
    <!-- Overlay untuk efek blur dan redup -->
    <div class="absolute inset-0 bg-black opacity-50 backdrop-blur-sm"></div>

    <!-- Konten di atas overlay -->
    <div class="relative text-center text-white px-4 w3-animate-zoom">
      <h1 class="text-4xl font-bold md:text-6xl">Yayasan Isyfa Lana Dhuafa</h1>
      <p class="mt-4 text-lg md:text-2xl">
        Membangun Harapan dan Kesejahteraan Bersama
      </p>
      <a
        href="#home"
        class="mt-6 inline-block bg-primary hover:bg-primary-dark text-white font-semibold py-2 px-6 rounded-lg transition duration-300 ease-in-out"
      >
        Lihat Selengkapnya
      </a>
    </div>
  </div>

  <hr class="my-12 h-0.5 border-t-0 bg-neutral-100 dark:bg-white/10" />
</template>
