<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const isNavVisible = ref(false);
const hamburger = ref(null);
const navMenu = ref(null);

function handleClickOutside(event) {
  if (
    hamburger.value &&
    navMenu.value &&
    !hamburger.value.contains(event.target) &&
    !navMenu.value.contains(event.target)
  ) {
    isNavVisible.value = false;
    isDropdownVisible.value = false;
  }
}

onMounted(() => {
  window.addEventListener("click", handleClickOutside);
});

onBeforeUnmount(() => {
  window.removeEventListener("click", handleClickOutside);
});

function closeNav() {
  isNavVisible.value = false;
}

// State untuk search bar, dropdown menu, dan query pencarian
const isSearchBarVisible = ref(false);
const isDropdownVisible = ref(false);
const searchQuery = ref("");

// Data contoh untuk pencarian
const items = ref([
  "Yayasan Isyfalana",
  "Donasi Pendidikan",
  "Bantuan Kesehatan",
  "Program Sosial",
  "Kesejahteraan Anak",
]);

// Hasil pencarian yang difilter
const filteredResults = ref([]);

// Fungsi untuk menampilkan/menghilangkan search bar
function toggleSearchBar() {
  isSearchBarVisible.value = !isSearchBarVisible.value;
  if (!isSearchBarVisible.value) {
    searchQuery.value = ""; // Reset query pencarian saat search bar ditutup
    filteredResults.value = []; // Reset hasil pencarian
  }
}

// Fungsi untuk menutup search bar saat klik di luar
function closeSearchBar() {
  isSearchBarVisible.value = false;
  searchQuery.value = ""; // Reset query pencarian
  filteredResults.value = []; // Reset hasil pencarian
}

// Fungsi untuk menampilkan/menghilangkan dropdown menu
function toggleDropdown() {
  isDropdownVisible.value = !isDropdownVisible.value;
}

// Fungsi untuk melakukan pencarian
function search() {
  if (searchQuery.value.trim() === "") {
    filteredResults.value = [];
    return;
  }
  // Filter data berdasarkan query pencarian
  filteredResults.value = items.value.filter((item) =>
    item.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
}
</script>

<template>
  <header
    class="top-0 left-0 w-full flex items-center z-[99] bg-white fixed w3-animate-top"
  >
    <div class="container">
      <div class="flex items-center justify-between relative">
        <div class="px-4">
          <a href="#home" class="font-bold p-1 block">
            <img src="/logo2.png" alt="" width="90px" />
          </a>
        </div>

        <div class="flex items-center px-4 lg:px-1">
          <i
            class="ph ph-magnifying-glass text-2xl font-semibold block lg:hidden mr-12 hover:scale-125"
            @click="toggleSearchBar"
          ></i>
          <button
            ref="hamburger"
            id="hamburger"
            name="hamburger"
            type="button"
            class="block absolute right-4 lg:hidden"
            @click="isNavVisible = !isNavVisible"
            :class="{ 'hamburger-active': isNavVisible }"
          >
            <span
              class="hamburger-line origin-top-left transition duration-300 ease-in-out"
            ></span>
            <span
              class="hamburger-line transition duration-300 ease-in-out"
            ></span>
            <span
              class="hamburger-line origin-bottom-left transition duration-300 ease-in-out"
            ></span>
          </button>
          <nav
            ref="navMenu"
            id="nav-menu"
            :class="{
              'translate-x-0': isNavVisible,
              '-translate-x-full': !isNavVisible,
            }"
            class="absolute py-5 bg-primary shadow-lg rounded-lg h-dvh w-full right-4 top-full transform transition-transform duration-300 ease-in-out lg:h-full lg:block lg:static lg:bg-transparent lg:max-w-full lg:shadow-none lg:rounded-none lg:translate-x-0"
          >
            <ul class="block lg:flex">
              <li class="group">
                <a
                  href="#home"
                  @click="closeNav"
                  class="text-base text-white lg:text-black font-semibold transition py-2 mx-8 flex lg:group-hover:text-primary"
                  >Beranda</a
                >
              </li>
              <li class="group">
                <button
                  @click="toggleDropdown"
                  class="text-base text-white lg:text-black font-semibold transition py-2 mx-8 lg:group-hover:text-primary hidden lg:flex"
                >
                  Tautan
                  <i class="ph ph-caret-down font-semibold text-lg ml-2"></i>
                </button>
                <div class="relative">
                  <ul
                    v-if="isDropdownVisible"
                    class="absolute mt-2 bg-white text-black rounded-lg shadow-lg py-2 w-40"
                  >
                    <li>
                      <a
                        href="https://arsip.yayasanisyfalanadhuafa.org/"
                        class="block px-4 py-2 hover:bg-gray-200"
                        >Dokumentasi</a
                      >
                    </li>
                    <li>
                      <a
                        href="https://yild-artikel.webflow.io/"
                        class="block px-4 py-2 hover:bg-gray-200"
                        >Laman Article</a
                      >
                    </li>
                    <li>
                      <a href="#link3" class="block px-4 py-2 hover:bg-gray-200"
                        >Link 3</a
                      >
                    </li>
                  </ul>
                </div>
                <select
                  @change="handleDropdownChange"
                  class="text-base text-white font-semibold transition py-2 mx-8 lg:group-hover:text-primary bg-transparent appearance-none cursor-pointer lg:hidden"
                >
                  <option selected disabled>Tautan &#9868;</option>
                  <option
                    value="https://arsip.yayasanisyfalanadhuafa.org/"
                    class="text-black"
                  >
                    Dokumentasi
                  </option>
                  <option
                    value="https://yild-artikel.webflow.io/"
                    class="text-black"
                  >
                    Laman Article
                  </option>
                  <option value="#link3" class="text-black">Link 3</option>
                </select>
              </li>
              <li class="group">
                <a
                  href="#tentang"
                  @click="closeNav"
                  class="text-base text-white lg:text-black font-semibold transition py-2 mx-8 flex lg:group-hover:text-primary"
                  >Tentang Kami</a
                >
              </li>
              <li class="group">
                <a
                  href="#program"
                  @click="closeNav"
                  class="text-base text-white lg:text-black font-semibold transition py-2 mx-8 flex lg:group-hover:text-primary"
                  >Program</a
                >
              </li>
              <li class="group">
                <a
                  href="#bergabung"
                  @click="closeNav"
                  class="text-base text-white lg:text-black font-semibold transition py-2 mx-8 flex lg:group-hover:text-primary"
                  >Bergabung</a
                >
              </li>
              <li>
                <i
                  class="ph ph-magnifying-glass text-2xl font-semibold hidden lg:block hover:scale-125"
                  @click="toggleSearchBar"
                ></i>
              </li>
              <li class="text-center pt-8">
                <p class="text-white lg:hidden font-bold">&copy;2024 YiLD</p>
              </li>
            </ul>
          </nav>
          <div
            v-if="isSearchBarVisible"
            class="fixed inset-0 bg-black bg-opacity-50 backdrop-blur-sm flex items-center justify-center z-10"
            @click="closeSearchBar"
          >
            <!-- Search Bar Container -->
            <div
              class="bg-white rounded-lg shadow-lg p-4 w-3/4 max-w-lg"
              @click.stop
            >
              <input
                type="text"
                v-model="searchQuery"
                @input="search"
                placeholder="Cari sesuatu..."
                class="w-full p-2 border rounded-lg focus:outline-none"
              />
              <!-- Hasil Pencarian -->
              <ul v-if="filteredResults.length" class="mt-4">
                <li
                  v-for="(result, index) in filteredResults"
                  :key="index"
                  class="py-2 border-b"
                >
                  {{ result }}
                </li>
              </ul>
              <p v-else class="mt-4 text-gray-500">
                Tidak ada hasil yang ditemukan
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>
