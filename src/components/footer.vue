<template>
  <footer class="bg-gray-800 text-white pt-10 pb-6">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <!-- Kontak -->
        <div>
          <h3 class="font-semibold text-lg mb-4 lg:text-xl">Kontak</h3>
          <p class="text-sm text-gray-300 lg:text-lg">Email: <a href="mailto:isyfalanadhuafa.01@gmail.com">isyfalanadhuafa.01@gmail.com</a></p>
          <p class="text-sm text-gray-300 lg:text-lg">
            Telepon: +62 812-2781-996, +62 896-0146-5301
          </p>
        </div>

        <!-- Alamat dengan Google Maps -->
        <div>
          <h3 class="font-semibold text-lg mb-4 lg:text-xl">Alamat</h3>
          <p class="text-sm text-gray-300 lg:text-lg">
            Jipangan, Bangunjiwo, Kec. Kasihan, Kabupaten Bantul, Daerah
            Istimewa Yogyakarta 55184
          </p>
          <div class="mt-4">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3952.429927949934!2d110.32492427412167!3d-7.84999167801246!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e7af95118818b81%3A0x489f435363a0b5e!2sKantor%20yayasan%20isyfa%20lana%20dhuafa!5e0!3m2!1sen!2sid!4v1731065922098!5m2!1sen!2sid"
              width="100%"
              height="150"
              style="border: 0"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>

        <!-- Sosial Media -->
        <div>
          <h3 class="font-semibold text-lg mb-4 lg:text-xl">Sosial Media</h3>
          <ul class="flex space-x-4">
            <li>
              <a
                href="https://www.facebook.com/isyfalana.dhuafa?mibextid=ZbWKwL"
                target="_blank"
                rel="noopener"
                class="text-gray-400 hover:text-white"
                ><i class="ph ph-facebook-logo text-4xl"></i
              ></a>
            </li>
            <li>
              <a
                href="https://www.instagram.com/yayasan_isyfalanadhuafa?igsh=c2xhMjdvMm9kZTlt"
                target="_blank"
                rel="noopener"
                class="text-gray-400 hover:text-white"
                ><i class="ph ph-instagram-logo text-4xl"></i
              ></a>
            </li>
            <li>
              <a
                href="https://www.tiktok.com/@isyfalanadhuafa?_t=8q2MPLJtdDk&_r=1"
                target="_blank"
                rel="noopener"
                class="text-gray-400 hover:text-white"
                ><i class="ph ph-tiktok-logo text-4xl"></i
              ></a>
            </li>
            <li>
              <a
                href="https://youtube.com/@isyfalanachannel846?si=9lqBTnKOdsZAkmLZ"
                target="_blank"
                rel="noopener"
                class="text-gray-400 hover:text-white"
                ><i class="ph ph-youtube-logo text-4xl"></i
              ></a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Tautan Penting -->
      <div
        class="mt-8 border-t border-gray-700 pt-6 flex flex-col md:flex-row justify-between text-center md:text-left"
      >
        <ul
          class="flex flex-col md:flex-row space-y-2 md:space-y-0 md:space-x-4"
        >
          <li>
            <a
              href="https://arsip.yayasanisyfalanadhuafa.org/"
              target="_blank"
              rel="noopener"
              class="text-gray-400 hover:text-white"
              >Dokumentasi</a
            >
          </li>
          <li>
            <a href="https://yild-artikel.webflow.io/" class="text-gray-400 hover:text-white"
              >Laman Artikel</a
            >
          </li>
        </ul>

        <!-- Copyright -->
        <p class="text-gray-500 text-lg md:text-xl mt-4 md:mt-0">
          &copy; 2024 YiLD. All Right Reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
footer {
  background-color: #1f2937; /* Warna abu-abu gelap */
}
</style>
