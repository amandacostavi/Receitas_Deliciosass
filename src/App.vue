<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
// Usando um placeholder genérico para a logo
const logo = 'https://placehold.co/32x32/ff8c00/ffffff?text=R'

const router = useRouter()
const q = ref('')
const isSearchOpen = ref(false)

function toggleSearch() {
  isSearchOpen.value = !isSearchOpen.value
}

function doSearch() {
  if (q.value.trim()) {
    router.push(`/search?q=${encodeURIComponent(q.value)}`)
    q.value = ''
    isSearchOpen.value = false
  }
}
</script>

<template>
  <div class="min-h-screen bg-[#f9fafb] flex flex-col font-sans text-gray-800">
    <nav class="flex items-center justify-between px-12 py-4 bg-white shadow-sm border-b border-gray-100">
      <router-link
        to="/"
        class="flex items-center space-x-2 text-orange-600 font-semibold text-lg hover:text-orange-700 transition"
      >
        <img :src="logo" alt="Logo do site" class="h-8 w-auto" />
        <span>Receitas Deliciosas</span>
      </router-link>

      <div class="flex items-center space-x-8 text-[15px]">
        <router-link
          to="/"
          exact-active-class="text-orange-600 font-medium"
          class="flex items-center space-x-1 hover:text-orange-500 transition"
        >
          <span class="text-[18px]">🏠</span>
          <span>Início</span>
        </router-link>

        <router-link
          to="/receitas"
          active-class="text-orange-600 font-medium"
          class="flex items-center space-x-1 hover:text-orange-500 transition"
        >
          <span class="text-[18px]">🍽️</span>
          <span>Receitas</span>
        </router-link>

        <router-link
          to="/favorites"
          active-class="text-orange-600 font-medium"
          class="flex items-center space-x-1 hover:text-orange-500 transition"
        >
          <span class="text-[18px]">❤️</span>
          <span>Favoritos</span>
        </router-link>

        <router-link
          to="/add"
          active-class="text-orange-600 font-medium"
          class="flex items-center space-x-1 hover:text-orange-500 transition"
        >
          <span class="text-[18px]">➕</span>
          <span>Adicionar</span>
        </router-link>
      </div>

      <div class="relative flex items-center">
        <div
          class="w-10 h-10 bg-orange-500 rounded-full flex items-center justify-center shadow-md cursor-pointer hover:bg-orange-600 transition"
          @click="toggleSearch"
        >
          <span class="text-white text-lg">🔍</span>
        </div>

        <input
          v-if="isSearchOpen"
          v-model="q"
          type="text"
          placeholder="Buscar receitas..."
          @keyup.enter="doSearch"
          class="absolute right-14 border border-gray-300 rounded-full px-4 py-1.5 text-sm focus:outline-none focus:ring-2 focus:ring-orange-400 transition w-52 bg-white"
        />
      </div>
    </nav>

    <main class="flex-1 flex flex-col p-6 overflow-auto items-center">

      <div class="w-full max-w-4xl">

        <div class="flex flex-col mb-4">

          <div class="flex items-center mb-1">
            <router-link to="/" class="text-gray-600 text-xl hover:text-gray-800 transition mr-4">
              &larr; </router-link>

            <h1 class="text-xl font-semibold text-gray-800 flex items-center">
              <span class="text-red-600 text-xl mr-2">❤️</span> Minhas Receitas Favoritas
            </h1>
          </div>

          <p class="text-sm text-gray-500 ml-8 -mt-2">0 receitas salvas</p>
        </div>

        <div class="bg-white rounded-lg shadow-sm border border-gray-200 text-center py-20 px-6">
          <div class="flex flex-col items-center">

            <div class="text-gray-300 text-6xl mb-4">♡</div>

            <p class="text-gray-700 text-base font-medium mb-1">Nenhuma receita favorita ainda</p>

            <p class="text-gray-500 text-sm mb-8">Comece a explorar e salvar suas receitas preferidas</p>

            <router-link
              to="/receitas"
              class="bg-orange-600 hover:bg-orange-700 text-white font-medium text-sm px-6 py-2.5 rounded shadow-md transition"
            >
              Explorar Receitas
            </router-link>
          </div>
        </div>

      </div>
    </main>
  </div>
</template>

<style scoped>
/* Nenhum CSS extra é necessário, pois estamos usando Tailwind (classes utility) */
</style>
