<template>
  <nav
    class="sticky top-0 z-50 bg-[#1a1f3a]/95 backdrop-blur-md shadow-lg border-b border-cyan-500/20"
  >
    <div class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16 sm:h-18">
        <!-- Left: Brand/Logo -->
        <div
          class="flex items-center space-x-2 sm:space-x-3 cursor-pointer group"
        >
          <div class="relative">
            <img
              src="/images/Ai-powerd-owl.png"
              alt="AI Trip Planner Logo"
              class="h-10 w-10 sm:h-12 sm:w-12 object-contain transform group-hover:scale-105 transition-all duration-300"
            />
          </div>
          <div>
            <h1
              class="text-lg sm:text-xl lg:text-2xl font-bold bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent"
            >
              AI Trip Planner
            </h1>
          </div>
        </div>

        <!-- Center: Main Navigation -->
        <div class="hidden lg:flex items-center space-x-8">
          <button
            @click="scrollToSection('hero')"
            class="text-gray-300 hover:text-cyan-400 font-semibold transition-colors"
          >
            Home
          </button>
          <button
            @click="scrollToSection('statistics')"
            class="text-gray-300 hover:text-cyan-400 font-semibold transition-colors"
          >
            Statistics
          </button>
          <NuxtLink to="/plan-trip">
            <button
              class="text-gray-300 hover:text-cyan-400 font-semibold transition-colors"
            >
              Generate
            </button>
          </NuxtLink>
          <button
            @click="scrollToSection('about')"
            class="text-gray-300 hover:text-cyan-400 font-semibold transition-colors"
          >
            About
          </button>
          <button
            @click="scrollToSection('contact')"
            class="text-gray-300 hover:text-cyan-400 font-semibold transition-colors"
          >
            Contact
          </button>
        </div>

        <!-- Right: Auth Buttons -->
        <div class="flex items-center space-x-3">
          <!-- Sign Up Button -->
          <NuxtLink to="/sign-up">
            <button
              class="hidden md:flex items-center px-6 py-2 text-gray-300 hover:text-cyan-400 font-medium transition-all border border-cyan-500/30 hover:border-cyan-400 rounded-full"
            >
              Signup
            </button>
          </NuxtLink>

          <!-- Login Button -->
          <NuxtLink to="/sign-in">
            <button
              class="hidden md:flex items-center px-6 py-2 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-600 hover:to-blue-700 text-white font-medium rounded-full transition-all duration-300 shadow-lg shadow-cyan-500/30"
            >
              Login
            </button>
          </NuxtLink>

          <!-- Mobile Menu Button -->
          <button
            @click="showMobileMenu = !showMobileMenu"
            class="lg:hidden text-gray-300 p-2 hover:bg-cyan-500/20 rounded-xl transition-all"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Navigation Menu with Better Styling -->
      <div
        v-if="showMobileMenu"
        class="lg:hidden py-5 border-t border-blue-700/30 animate-fade-in"
      >
        <div class="flex flex-col space-y-3">
          <button
            @click="
              scrollToSection('hero');
              showMobileMenu = false;
            "
            :class="[
              'px-5 py-3.5 rounded-xl font-semibold text-left transition-all',
              activeNav === 'hero'
                ? 'bg-gradient-to-r from-cyan-400 to-blue-500 text-white shadow-lg shadow-cyan-500/30'
                : 'text-gray-300 hover:bg-gradient-to-r hover:from-cyan-400/20 hover:to-blue-500/20 hover:text-white',
            ]"
          >
            🏠 Home
          </button>
          <button
            @click="
              scrollToSection('statistics');
              showMobileMenu = false;
            "
            :class="[
              'px-5 py-3.5 rounded-xl font-semibold text-left transition-all',
              activeNav === 'statistics'
                ? 'bg-gradient-to-r from-purple-400 to-pink-500 text-white shadow-lg shadow-purple-500/30'
                : 'text-gray-300 hover:bg-gradient-to-r hover:from-purple-400/20 hover:to-pink-500/20 hover:text-white',
            ]"
          >
            📊 Statistics
          </button>
          <NuxtLink to="/plan-trip" @click="showMobileMenu = false">
            <button
              :class="[
                'w-full px-5 py-3.5 rounded-xl font-semibold text-left transition-all',
                $route.path === '/plan-trip'
                  ? 'bg-gradient-to-r from-green-400 to-emerald-500 text-white shadow-lg shadow-green-500/30'
                  : 'text-gray-300 hover:bg-gradient-to-r hover:from-green-400/20 hover:to-emerald-500/20 hover:text-white',
              ]"
            >
              Generate
            </button>
          </NuxtLink>

          <!-- About Us with Dropdown -->
          <div>
            <button
              @click="showAboutDropdown = !showAboutDropdown"
              :class="[
                'w-full px-5 py-3.5 rounded-xl font-semibold text-left transition-all flex items-center justify-between',
                activeNav === 'about' || showAboutDropdown
                  ? 'bg-gradient-to-r from-orange-400 to-red-500 text-white shadow-lg shadow-orange-500/30'
                  : 'text-gray-300 hover:bg-gradient-to-r hover:from-orange-400/20 hover:to-red-500/20 hover:text-white',
              ]"
            >
              <span>ℹ️ About Us</span>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-4 w-4 transition-transform duration-300"
                :class="{ 'rotate-180': showAboutDropdown }"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                />
              </svg>
            </button>

            <!-- Dropdown Items -->
            <div v-if="showAboutDropdown" class="mt-2 ml-6 space-y-2">
              <a
                href="#choose-our-service"
                @click="
                  showMobileMenu = false;
                  showAboutDropdown = false;
                  activeNav = 'about';
                "
                class="block px-4 py-2.5 text-sm text-gray-300 hover:text-white hover:bg-white/10 rounded-lg transition-all"
              >
                📋 Choose Our Service
              </a>
              <a
                href="#why-choose-us"
                @click="
                  showMobileMenu = false;
                  showAboutDropdown = false;
                  activeNav = 'about';
                "
                class="block px-4 py-2.5 text-sm text-gray-300 hover:text-white hover:bg-white/10 rounded-lg transition-all"
              >
                Why Choose Our Service
              </a>
              <a
                href="#guest-reviews"
                @click="
                  showMobileMenu = false;
                  showAboutDropdown = false;
                  activeNav = 'about';
                "
                class="block px-4 py-2.5 text-sm text-gray-300 hover:text-white hover:bg-white/10 rounded-lg transition-all"
              >
                💬 Guest Reviews
              </a>
            </div>
          </div>

          <button
            @click="
              scrollToSection('contact');
              showMobileMenu = false;
            "
            :class="[
              'px-5 py-3.5 rounded-xl font-semibold text-left transition-all',
              activeNav === 'contact'
                ? 'bg-gradient-to-r from-pink-400 to-rose-500 text-white shadow-lg shadow-pink-500/30'
                : 'text-gray-300 hover:bg-gradient-to-r hover:from-pink-400/20 hover:to-rose-500/20 hover:text-white',
            ]"
          >
            📧 Contact
          </button>
          <div
            class="border-t border-blue-700/30 pt-4 mt-2 space-y-3 md:hidden"
          >
            <NuxtLink to="/sign-in">
              <button
                class="w-full px-5 py-3.5 text-gray-300 hover:bg-white/10 hover:text-white rounded-xl text-left font-semibold transition-all"
              >
                🔑 Log In
              </button>
            </NuxtLink>
            <NuxtLink to="/sign-up">
              <button
                class="w-full px-5 py-3.5 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold rounded-xl shadow-lg transform hover:scale-105 transition-all"
              >
                🚀 Sign Up
              </button>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";

const showMobileMenu = ref(false);
const showAboutDropdown = ref(false);
const activeNav = ref("hero");

const scrollToSection = (section) => {
  const element = document.getElementById(section);
  if (element) {
    element.scrollIntoView({ behavior: "smooth", block: "start" });
    activeNav.value = section;
  }
};
</script>
