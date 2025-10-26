<template>
  <div
    class="min-h-screen bg-gradient-to-br from-[#0a0820] via-[#1a1040] to-[#0f0a30]"
  >
    <!-- Modern Navigation Bar with Better Spacing -->
    <nav
      class="sticky top-0 z-50 bg-gradient-to-r from-[#0a0820]/95 via-[#1a1040]/95 to-[#0f0a30]/95 border-b border-purple-700/20 shadow-2xl backdrop-blur-md"
    >
      <div class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16 sm:h-20 lg:h-24">
          <!-- Left: Brand/Logo with Better Spacing -->
          <div
            class="flex items-center space-x-2 sm:space-x-3 cursor-pointer group"
          >
            <div class="relative">
              <div
                class="absolute inset-0 bg-gradient-to-r from-cyan-400 to-blue-500 rounded-lg sm:rounded-xl blur-lg opacity-50 group-hover:opacity-70 transition-opacity"
              ></div>
              <div
                class="relative bg-gradient-to-br from-cyan-500 via-blue-500 to-indigo-600 p-2.5 sm:p-3 rounded-lg sm:rounded-xl shadow-2xl transform group-hover:scale-110 transition-all duration-300"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 sm:h-6 sm:w-6 text-white"
                  fill="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M21 16v-2l-8-5V3.5c0-.83-.67-1.5-1.5-1.5S10 2.67 10 3.5V9l-8 5v2l8-2.5V19l-2 1.5V22l3.5-1 3.5 1v-1.5L13 19v-5.5l8 2.5z"
                  />
                </svg>
              </div>
            </div>
            <div>
              <h1
                class="text-base sm:text-xl lg:text-2xl font-bold text-white group-hover:text-cyan-200 transition-colors"
              >
                AI Trip Planner
              </h1>
            </div>
          </div>

          <!-- Center: Main Navigation with Better Spacing -->
          <div
            class="hidden lg:flex items-center space-x-1.5 bg-white/5 rounded-2xl p-2.5 backdrop-blur-sm border border-white/10 shadow-xl shadow-purple-500/10"
          >
            <button
              @click="scrollToSection('hero')"
              :class="[
                'px-7 py-3.5 rounded-xl font-semibold transition-all duration-300 text-sm tracking-wide',
                activeNav === 'hero'
                  ? 'bg-gradient-to-r from-cyan-400 to-blue-500 text-white shadow-lg shadow-cyan-500/40 scale-105'
                  : 'text-gray-300 hover:text-white hover:bg-gradient-to-r hover:from-cyan-400/20 hover:to-blue-500/20 hover:scale-105',
              ]"
            >
              Home
            </button>
            <button
              @click="scrollToSection('statistics')"
              :class="[
                'px-7 py-3.5 rounded-xl font-semibold transition-all duration-300 text-sm tracking-wide',
                activeNav === 'statistics'
                  ? 'bg-gradient-to-r from-purple-400 to-pink-500 text-white shadow-lg shadow-purple-500/40 scale-105'
                  : 'text-gray-300 hover:text-white hover:bg-gradient-to-r hover:from-purple-400/20 hover:to-pink-500/20 hover:scale-105',
              ]"
            >
              Statistics
            </button>
            <NuxtLink to="/plan-trip">
              <button
                :class="[
                  'px-7 py-3.5 rounded-xl font-semibold transition-all duration-300 text-sm tracking-wide',
                  $route.path === '/plan-trip'
                    ? 'bg-gradient-to-r from-green-400 to-emerald-500 text-white shadow-lg shadow-green-500/40 scale-105'
                    : 'text-gray-300 hover:text-white hover:bg-gradient-to-r hover:from-green-400/20 hover:to-emerald-500/20 hover:scale-105',
                ]"
              >
                Generate
              </button>
            </NuxtLink>

            <!-- About Us with Dropdown -->
            <div class="relative">
              <button
                @click="showAboutDropdown = !showAboutDropdown"
                :class="[
                  'px-7 py-3.5 rounded-xl font-semibold transition-all duration-300 text-sm tracking-wide flex items-center gap-2',
                  activeNav === 'about' || showAboutDropdown
                    ? 'bg-gradient-to-r from-orange-400 to-red-500 text-white shadow-lg shadow-orange-500/40 scale-105'
                    : 'text-gray-300 hover:text-white hover:bg-gradient-to-r hover:from-orange-400/20 hover:to-red-500/20 hover:scale-105',
                ]"
              >
                About Us
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

              <!-- Dropdown Menu -->
              <div
                v-if="showAboutDropdown"
                class="absolute top-full mt-2 w-64 bg-white/10 backdrop-blur-xl rounded-xl shadow-2xl border border-white/20 overflow-hidden animate-fade-in"
              >
                <a
                  href="#choose-our-service"
                  @click="
                    showAboutDropdown = false;
                    activeNav = 'about';
                  "
                  class="block px-5 py-3 text-white hover:bg-white/10 transition-all duration-300 border-b border-white/10"
                >
                  <div class="font-semibold text-sm">Choose Our Service</div>
                  <div class="text-xs text-gray-400 mt-0.5">
                    Explore our travel services
                  </div>
                </a>
                <a
                  href="#why-choose-us"
                  @click="
                    showAboutDropdown = false;
                    activeNav = 'about';
                  "
                  class="block px-5 py-3 text-white hover:bg-white/10 transition-all duration-300 border-b border-white/10"
                >
                  <div class="font-semibold text-sm">
                    Why Choose Our Service
                  </div>
                  <div class="text-xs text-gray-400 mt-0.5">
                    See what makes us special
                  </div>
                </a>
                <a
                  href="#guest-reviews"
                  @click="
                    showAboutDropdown = false;
                    activeNav = 'about';
                  "
                  class="block px-5 py-3 text-white hover:bg-white/10 transition-all duration-300"
                >
                  <div class="font-semibold text-sm">Guest Reviews</div>
                  <div class="text-xs text-gray-400 mt-0.5">
                    Read testimonials from travelers
                  </div>
                </a>
              </div>
            </div>

            <button
              @click="scrollToSection('contact')"
              :class="[
                'px-7 py-3.5 rounded-xl font-semibold transition-all duration-300 text-sm tracking-wide',
                activeNav === 'contact'
                  ? 'bg-gradient-to-r from-pink-400 to-rose-500 text-white shadow-lg shadow-pink-500/40 scale-105'
                  : 'text-gray-300 hover:text-white hover:bg-gradient-to-r hover:from-pink-400/20 hover:to-rose-500/20 hover:scale-105',
              ]"
            >
              Contact
            </button>
          </div>

          <!-- Right: Auth Buttons with Better Spacing -->
          <div class="flex items-center space-x-3 sm:space-x-4">
            <!-- Log In Button -->
            <NuxtLink to="/sign-in">
              <button
                class="hidden md:flex items-center px-6 py-2.5 text-gray-300 hover:text-white font-semibold transition-all hover:bg-white/5 rounded-xl border border-white/10 hover:border-white/20"
              >
                Log In
              </button>
            </NuxtLink>

            <!-- Sign Up Button -->
            <NuxtLink to="/sign-up">
              <button
                class="hidden md:flex items-center px-7 py-2.5 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold rounded-xl shadow-lg shadow-cyan-500/30 hover:shadow-xl hover:shadow-cyan-500/50 transition-all duration-300 transform hover:scale-105"
              >
                Sign Up
              </button>
            </NuxtLink>

            <!-- Mobile Menu Button -->
            <button
              @click="showMobileMenu = !showMobileMenu"
              class="lg:hidden text-white p-2 hover:bg-white/10 rounded-xl transition-all"
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
                ✨ Generate
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
                  ⭐ Why Choose Our Service
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

    <!-- Hero Section with Clean Background -->
    <div id="hero" class="relative min-h-[calc(100vh-96px)] overflow-hidden">
      <!-- Animated Starry Background -->
      <div class="absolute inset-0 stars-container">
        <div class="stars-layer stars-layer-1"></div>
        <div class="stars-layer stars-layer-2"></div>
        <div class="stars-layer stars-layer-3"></div>
      </div>

      <!-- Subtle Globe Background (smaller and less prominent) -->
      <div class="absolute inset-0 flex items-center justify-center opacity-20">
        <!-- Globe Container -->
        <div class="relative w-full max-w-5xl aspect-square">
          <!-- Globe with glow effect -->
          <div class="absolute inset-0 flex items-center justify-center">
            <div class="relative w-full h-full">
              <!-- Outer glow -->
              <div
                class="absolute inset-0 bg-gradient-to-br from-cyan-500/20 via-blue-500/20 to-purple-500/20 rounded-full blur-3xl animate-pulse"
              ></div>

              <!-- Main globe - Realistic Earth -->
              <div
                class="absolute inset-0 rounded-full shadow-2xl overflow-hidden border border-white/20"
                style="
                  background: radial-gradient(
                    circle at 30% 30%,
                    rgba(100, 180, 255, 0.4) 0%,
                    rgba(30, 100, 200, 0.5) 25%,
                    rgba(20, 60, 150, 0.6) 50%,
                    rgba(10, 40, 100, 0.7) 75%,
                    rgba(5, 20, 60, 0.8) 100%
                  );
                "
              >
                <!-- Ocean base -->
                <div
                  class="absolute inset-0 bg-gradient-to-br from-blue-500/50 via-blue-600/60 to-blue-900/70"
                ></div>

                <!-- Clouds layer -->
                <div class="absolute inset-0 opacity-40">
                  <div
                    class="absolute top-[10%] left-[15%] w-40 h-20 bg-white/60 rounded-full blur-xl"
                  ></div>
                  <div
                    class="absolute top-[25%] right-[20%] w-48 h-24 bg-white/50 rounded-full blur-2xl"
                  ></div>
                  <div
                    class="absolute bottom-[30%] left-[25%] w-44 h-22 bg-white/55 rounded-full blur-xl"
                  ></div>
                  <div
                    class="absolute bottom-[15%] right-[30%] w-36 h-18 bg-white/45 rounded-full blur-xl"
                  ></div>
                </div>

                <!-- Continents/landmasses -->
                <div class="absolute inset-0">
                  <!-- North America -->
                  <div
                    class="absolute top-[20%] left-[15%] w-28 h-32 bg-green-600/60 rounded-[40%] blur-sm"
                  ></div>
                  <div
                    class="absolute top-[25%] left-[20%] w-24 h-28 bg-emerald-700/50 rounded-[35%] blur-sm"
                  ></div>

                  <!-- Europe/Africa -->
                  <div
                    class="absolute top-[30%] right-[25%] w-32 h-36 bg-green-700/55 rounded-[45%] blur-sm"
                  ></div>
                  <div
                    class="absolute top-[40%] right-[28%] w-28 h-32 bg-yellow-800/40 rounded-[40%] blur-sm"
                  ></div>

                  <!-- South America -->
                  <div
                    class="absolute bottom-[25%] left-[30%] w-20 h-28 bg-green-600/50 rounded-[50%] blur-sm"
                  ></div>

                  <!-- Asia -->
                  <div
                    class="absolute top-[35%] right-[15%] w-36 h-32 bg-green-600/45 rounded-[38%] blur-sm"
                  ></div>
                </div>

                <!-- Atmosphere glow -->
                <div
                  class="absolute inset-0 rounded-full bg-gradient-to-br from-cyan-400/20 via-transparent to-transparent"
                ></div>

                <!-- Rotating shine effect -->
                <div
                  class="absolute inset-0 bg-gradient-to-br from-white/15 via-transparent to-transparent animate-spin-slow"
                ></div>

                <!-- Grid overlay for dimension -->
                <div class="absolute inset-0 opacity-10">
                  <div
                    class="h-full w-full"
                    style="
                      background-image: repeating-linear-gradient(
                          0deg,
                          transparent,
                          transparent 35px,
                          rgba(255, 255, 255, 0.15) 35px,
                          rgba(255, 255, 255, 0.15) 36px
                        ),
                        repeating-linear-gradient(
                          90deg,
                          transparent,
                          transparent 35px,
                          rgba(255, 255, 255, 0.15) 35px,
                          rgba(255, 255, 255, 0.15) 36px
                        );
                    "
                  ></div>
                </div>
              </div>

              <!-- Flight paths -->
              <svg class="absolute inset-0 w-full h-full" viewBox="0 0 400 400">
                <defs>
                  <linearGradient
                    id="pathGradient"
                    x1="0%"
                    y1="0%"
                    x2="100%"
                    y2="0%"
                  >
                    <stop
                      offset="0%"
                      style="
                        stop-color: rgba(255, 255, 255, 0);
                        stop-opacity: 0;
                      "
                    />
                    <stop
                      offset="50%"
                      style="
                        stop-color: rgba(255, 255, 255, 0.8);
                        stop-opacity: 1;
                      "
                    />
                    <stop
                      offset="100%"
                      style="
                        stop-color: rgba(255, 255, 255, 0);
                        stop-opacity: 0;
                      "
                    />
                  </linearGradient>
                </defs>
                <path
                  d="M 80,180 Q 200,120 320,180"
                  stroke="url(#pathGradient)"
                  stroke-width="2"
                  fill="none"
                  stroke-dasharray="5,5"
                  class="animate-dash"
                />
                <path
                  d="M 100,250 Q 200,300 300,240"
                  stroke="url(#pathGradient)"
                  stroke-width="2"
                  fill="none"
                  stroke-dasharray="5,5"
                  class="animate-dash-slow"
                />
              </svg>

              <!-- Location markers -->
              <div
                class="absolute top-1/4 left-1/5 w-3 h-3 bg-yellow-400 rounded-full shadow-lg animate-pulse"
              ></div>
              <div
                class="absolute top-1/3 right-1/4 w-3 h-3 bg-yellow-400 rounded-full shadow-lg animate-pulse"
                style="animation-delay: 0.5s"
              ></div>
              <div
                class="absolute bottom-1/3 left-1/3 w-3 h-3 bg-yellow-400 rounded-full shadow-lg animate-pulse"
                style="animation-delay: 1s"
              ></div>
            </div>
          </div>
        </div>

        <!-- Floating stars/dots -->
        <div
          class="absolute top-20 left-20 w-1 h-1 bg-white rounded-full animate-pulse"
        ></div>
        <div
          class="absolute top-40 right-32 w-1 h-1 bg-white rounded-full animate-pulse"
          style="animation-delay: 0.5s"
        ></div>
        <div
          class="absolute bottom-32 left-40 w-1 h-1 bg-white rounded-full animate-pulse"
          style="animation-delay: 1s"
        ></div>
        <div
          class="absolute bottom-48 right-48 w-1 h-1 bg-white rounded-full animate-pulse"
          style="animation-delay: 1.5s"
        ></div>
      </div>

      <!-- Hero Content -->
      <div
        class="relative z-10 flex items-center justify-center min-h-[calc(100vh-96px)] py-16"
      >
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <!-- Badge at top -->
          <div
            class="flex justify-center items-center mb-6 sm:mb-8 animate-fade-in px-4"
          >
            <div
              class="flex items-center space-x-2 sm:space-x-3 bg-white/10 backdrop-blur-md rounded-full px-4 sm:px-6 py-2 sm:py-3 border border-white/20"
            >
              <span
                class="px-2 sm:px-3 py-1 bg-white text-gray-900 text-[10px] sm:text-xs font-bold rounded-full uppercase"
                >New</span
              >
              <span class="text-gray-300 text-xs sm:text-sm font-medium"
                >AI-Powered Trip Planning</span
              >
            </div>
          </div>

          <!-- Main Heading -->
          <h1
            class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-extrabold text-white mb-6 leading-[1.15] tracking-tight"
            style="text-shadow: 0 4px 20px rgba(0, 0, 0, 0.5)"
          >
            Plan your travel
            <br />
            <span
              class="bg-gradient-to-r from-cyan-300 via-blue-300 to-purple-300 bg-clip-text text-transparent"
            >
              with AI
            </span>
          </h1>

          <!-- Subtitle -->
          <p
            class="text-base sm:text-lg md:text-xl text-gray-300/90 mb-8 max-w-2xl mx-auto leading-relaxed"
            style="text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3)"
          >
            Smarter than endless tabs, a personalized trip builder and itinerary
            generator that saves you hours planning flights, hotels, and
            activities.
          </p>

          <!-- CTA Button -->
          <div class="flex justify-center items-center mt-6 sm:mt-8 px-4">
            <NuxtLink to="/plan-trip">
              <button
                class="group px-8 sm:px-10 md:px-12 py-4 sm:py-5 bg-gradient-to-r from-[#FFD700] via-[#FFC700] to-[#FFB800] hover:from-[#FFC700] hover:via-[#FFB800] hover:to-[#FFA500] text-gray-900 font-bold rounded-full shadow-[0_10px_40px_rgba(255,193,7,0.5)] hover:shadow-[0_15px_60px_rgba(255,193,7,0.7)] transition-all duration-500 transform hover:scale-[1.05] text-base sm:text-lg md:text-xl whitespace-nowrap relative overflow-hidden"
              >
                <span
                  class="absolute inset-0 bg-gradient-to-r from-yellow-300 to-orange-300 opacity-0 group-hover:opacity-20 transition-opacity duration-500"
                ></span>
                <span class="relative">Generate Your Trip with AI</span>
              </button>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>

    <!-- Statistics Section -->
    <div
      id="statistics"
      class="py-8 sm:py-12 lg:py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#0a0820] to-[#0f1535]"
    >
      <div class="max-w-6xl mx-auto">
        <!-- Section Header -->
        <div class="text-center mb-8 sm:mb-10">
          <h2
            class="text-2xl sm:text-3xl md:text-4xl font-bold text-white mb-2 sm:mb-3"
          >
            Travel Statistics
          </h2>
          <p class="text-sm sm:text-base text-gray-400 max-w-xl mx-auto">
            Track and analyze your travel activities
          </p>
        </div>

        <!-- Statistics Grid -->
        <div
          class="flex flex-col lg:flex-row items-stretch justify-center gap-5 lg:gap-6 max-w-5xl mx-auto"
        >
          <!-- Activity Section -->
          <div
            class="w-full lg:w-[48%] backdrop-blur-xl bg-gradient-to-br from-[#1a2844]/80 to-[#0f1a30]/80 rounded-2xl p-5 sm:p-6 border border-white/10 shadow-xl hover:shadow-cyan-500/10 transition-all duration-300 flex flex-col"
          >
            <div class="flex justify-between items-center mb-5">
              <h3
                class="text-lg sm:text-xl font-bold text-white flex items-center gap-2"
              >
                <span class="text-xl">✈️</span>
                Activity
              </h3>
              <button
                class="flex items-center gap-1.5 text-xs text-gray-400 hover:text-cyan-400 transition-colors px-2.5 py-1 rounded-lg hover:bg-white/5"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-3.5 w-3.5"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                  />
                </svg>
                <span class="hidden sm:inline">Search</span>
              </button>
            </div>

            <!-- Activity List -->
            <div class="space-y-2.5">
              <!-- Activity Item 1 -->
              <div
                class="flex items-center justify-between p-3 bg-gradient-to-r from-[#1e3a5f]/50 to-[#1a2f4d]/50 rounded-xl hover:from-[#1e3a5f]/70 hover:to-[#1a2f4d]/70 transition-all duration-300 border border-white/5 hover:border-cyan-500/20"
              >
                <div class="flex items-center space-x-2.5 flex-1 min-w-0">
                  <div
                    class="w-9 h-9 rounded-full bg-gradient-to-br from-cyan-400 to-blue-600 flex items-center justify-center text-white font-bold text-xs shadow-lg flex-shrink-0"
                  >
                    JN
                  </div>
                  <div class="min-w-0 flex-1">
                    <h4 class="text-white font-semibold text-sm truncate">
                      Jane Noor
                    </h4>
                    <p class="text-gray-400 text-xs truncate">
                      Chicago → LAGOS PM
                    </p>
                  </div>
                </div>
                <div class="flex items-center gap-2 flex-shrink-0">
                  <div
                    class="text-[10px] px-2 py-0.5 bg-gradient-to-r from-gray-700 to-gray-800 text-white rounded-full font-medium border border-gray-600"
                  >
                    HAC 33M
                  </div>
                  <div
                    class="px-2 py-0.5 bg-gradient-to-r from-green-500/20 to-emerald-500/20 border border-green-500/30 rounded-md"
                  >
                    <p class="text-green-400 text-[10px] font-semibold">
                      Take Off
                    </p>
                  </div>
                </div>
              </div>

              <!-- Activity Item 2 -->
              <div
                class="flex items-center justify-between p-3 bg-gradient-to-r from-[#1e3a5f]/50 to-[#1a2f4d]/50 rounded-xl hover:from-[#1e3a5f]/70 hover:to-[#1a2f4d]/70 transition-all duration-300 border border-white/5 hover:border-purple-500/20"
              >
                <div class="flex items-center space-x-2.5 flex-1 min-w-0">
                  <div
                    class="w-9 h-9 rounded-full bg-gradient-to-br from-purple-400 to-pink-600 flex items-center justify-center text-white font-bold text-xs shadow-lg flex-shrink-0"
                  >
                    AP
                  </div>
                  <div class="min-w-0 flex-1">
                    <h4 class="text-white font-semibold text-sm truncate">
                      Alex Perez
                    </h4>
                    <p class="text-gray-400 text-xs truncate">
                      Chicago → LAGOS PM
                    </p>
                  </div>
                </div>
                <div class="flex items-center gap-2 flex-shrink-0">
                  <div
                    class="text-[10px] px-2 py-0.5 bg-gradient-to-r from-yellow-500 to-orange-500 text-gray-900 rounded-full font-bold border border-yellow-400 shadow-md"
                  >
                    AIL 1844
                  </div>
                  <div
                    class="px-2 py-0.5 bg-gradient-to-r from-yellow-500/20 to-orange-500/20 border border-yellow-500/30 rounded-md"
                  >
                    <p class="text-yellow-400 text-[10px] font-semibold">
                      Pending
                    </p>
                  </div>
                </div>
              </div>

              <!-- Activity Item 3 -->
              <div
                class="flex items-center justify-between p-3 bg-gradient-to-r from-[#1e3a5f]/50 to-[#1a2f4d]/50 rounded-xl hover:from-[#1e3a5f]/70 hover:to-[#1a2f4d]/70 transition-all duration-300 border border-white/5 hover:border-green-500/20"
              >
                <div class="flex items-center space-x-2.5 flex-1 min-w-0">
                  <div
                    class="w-9 h-9 rounded-full bg-gradient-to-br from-green-400 to-emerald-600 flex items-center justify-center text-white font-bold text-xs shadow-lg flex-shrink-0"
                  >
                    JM
                  </div>
                  <div class="min-w-0 flex-1">
                    <h4 class="text-white font-semibold text-sm truncate">
                      John Mutunga
                    </h4>
                    <p class="text-gray-400 text-xs truncate">
                      Virginia → SAN-B
                    </p>
                  </div>
                </div>
                <div class="flex items-center gap-2 flex-shrink-0">
                  <div
                    class="text-[10px] px-2 py-0.5 bg-gradient-to-r from-gray-700 to-gray-800 text-white rounded-full font-medium border border-gray-600"
                  >
                    HAC 2M6
                  </div>
                  <div
                    class="px-2 py-0.5 bg-gradient-to-r from-blue-500/20 to-cyan-500/20 border border-blue-500/30 rounded-md"
                  >
                    <p class="text-blue-400 text-[10px] font-semibold">
                      Arrived
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Travel Activity Chart -->
          <div
            class="w-full lg:w-[48%] backdrop-blur-xl bg-gradient-to-br from-[#1a2844]/80 to-[#0f1a30]/80 rounded-2xl p-5 sm:p-6 border border-white/10 shadow-xl hover:shadow-purple-500/10 transition-all duration-300 flex flex-col"
          >
            <!-- Left Side: Stats -->
            <div class="flex items-stretch gap-4 h-full">
              <!-- Stats Section -->
              <div class="flex-1 flex flex-col justify-between">
                <!-- Header -->
                <div class="mb-auto">
                  <h3
                    class="text-base sm:text-lg font-semibold text-white mb-1"
                  >
                    Travel activity
                  </h3>
                  <p class="text-xs text-gray-400">Jane Noor</p>
                </div>

                <!-- 89% Stats -->
                <div class="mt-auto">
                  <h2 class="text-5xl sm:text-6xl font-bold text-white mb-2">
                    89%
                  </h2>
                  <p
                    class="text-xs text-gray-400 leading-relaxed max-w-[200px]"
                  >
                    89% of your travels have arrived on time to the destination.
                  </p>
                </div>
              </div>

              <!-- Chart Section -->
              <div class="flex items-end gap-2 sm:gap-2.5 w-32 sm:w-40">
                <!-- Bar 1 -->
                <div class="flex-1 flex flex-col items-center group">
                  <div class="relative w-full" style="height: 140px">
                    <div
                      class="absolute bottom-0 w-full bg-gradient-to-t from-cyan-400 to-cyan-300 rounded-t-md transition-all duration-500 group-hover:from-cyan-300 group-hover:to-cyan-200"
                      style="height: 60%"
                    ></div>
                  </div>
                </div>
                <!-- Bar 2 -->
                <div class="flex-1 flex flex-col items-center group">
                  <div class="relative w-full" style="height: 140px">
                    <div
                      class="absolute bottom-0 w-full bg-gradient-to-t from-cyan-400 to-cyan-300 rounded-t-md transition-all duration-500 group-hover:from-cyan-300 group-hover:to-cyan-200"
                      style="height: 85%"
                    ></div>
                  </div>
                </div>
                <!-- Bar 3 -->
                <div class="flex-1 flex flex-col items-center group">
                  <div class="relative w-full" style="height: 140px">
                    <div
                      class="absolute bottom-0 w-full bg-gradient-to-t from-cyan-400 to-cyan-300 rounded-t-md transition-all duration-500 group-hover:from-cyan-300 group-hover:to-cyan-200"
                      style="height: 50%"
                    ></div>
                  </div>
                </div>
                <!-- Bar 4 -->
                <div class="flex-1 flex flex-col items-center group">
                  <div class="relative w-full" style="height: 140px">
                    <div
                      class="absolute bottom-0 w-full bg-gradient-to-t from-cyan-400 to-cyan-300 rounded-t-md transition-all duration-500 group-hover:from-cyan-300 group-hover:to-cyan-200"
                      style="height: 100%"
                    ></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- AI Trip Builder Section -->
    <div
      class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#0f1535] to-[#0a0820]"
    >
      <div class="max-w-6xl mx-auto">
        <!-- Section Header -->
        <div class="text-center mb-10 sm:mb-12">
          <h2
            class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3 sm:mb-4"
          >
            <span class="text-green-400">AI</span> Create Your Dream Trip Plan
          </h2>
          <p class="text-sm sm:text-base text-gray-400 max-w-2xl mx-auto">
            Select one option from each category and let AI create your perfect
            itinerary
          </p>
        </div>

        <!-- Options Grid -->
        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-5 mb-8"
        >
          <!-- Destination -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-xl p-4 border border-white/10 hover:border-green-500/30 transition-all duration-300 cursor-pointer group"
          >
            <div class="flex items-center gap-3 mb-2">
              <div
                class="w-10 h-10 rounded-full bg-green-600/80 flex items-center justify-center group-hover:bg-green-500 transition-colors"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 text-white"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
                  />
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
                  />
                </svg>
              </div>
              <div class="flex-1">
                <p class="text-xs text-gray-400">Where to go</p>
                <h3 class="text-base font-semibold text-white">
                  Paris, France
                </h3>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-400 group-hover:text-white transition-colors"
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
            </div>
            <p class="text-xs text-gray-500">Select destination</p>
          </div>

          <!-- Budget -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-xl p-4 border border-white/10 hover:border-green-500/30 transition-all duration-300 cursor-pointer group"
          >
            <div class="flex items-center gap-3 mb-2">
              <div
                class="w-10 h-10 rounded-full bg-green-600/80 flex items-center justify-center group-hover:bg-green-500 transition-colors"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 text-white"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>
              <div class="flex-1">
                <p class="text-xs text-gray-400">Budget</p>
                <h3 class="text-base font-semibold text-white">
                  $2,000 - $5,000
                </h3>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-400 group-hover:text-white transition-colors"
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
            </div>
            <p class="text-xs text-gray-500">USD</p>
          </div>

          <!-- Duration -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-xl p-4 border border-white/10 hover:border-green-500/30 transition-all duration-300 cursor-pointer group"
          >
            <div class="flex items-center gap-3 mb-2">
              <div
                class="w-10 h-10 rounded-full bg-green-600/80 flex items-center justify-center group-hover:bg-green-500 transition-colors"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 text-white"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
                  />
                </svg>
              </div>
              <div class="flex-1">
                <p class="text-xs text-gray-400">Trip Duration</p>
                <h3 class="text-base font-semibold text-white">5 Days</h3>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-400 group-hover:text-white transition-colors"
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
            </div>
            <p class="text-xs text-gray-500">Travel period</p>
          </div>

          <!-- Travel Type -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-xl p-4 border border-white/10 hover:border-green-500/30 transition-all duration-300 cursor-pointer group"
          >
            <div class="flex items-center gap-3 mb-2">
              <div
                class="w-10 h-10 rounded-full bg-green-600/80 flex items-center justify-center group-hover:bg-green-500 transition-colors"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 text-white"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"
                  />
                </svg>
              </div>
              <div class="flex-1">
                <p class="text-xs text-gray-400">Travel Type</p>
                <h3 class="text-base font-semibold text-white">Luxury</h3>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-400 group-hover:text-white transition-colors"
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
            </div>
            <p class="text-xs text-gray-500">Entertainment</p>
          </div>

          <!-- Transportation -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-xl p-4 border border-white/10 hover:border-green-500/30 transition-all duration-300 cursor-pointer group"
          >
            <div class="flex items-center gap-3 mb-2">
              <div
                class="w-10 h-10 rounded-full bg-green-600/80 flex items-center justify-center group-hover:bg-green-500 transition-colors"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 text-white"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8 7h12m0 0l-4-4m4 4l-4 4m0 6H4m0 0l4 4m-4-4l4-4"
                  />
                </svg>
              </div>
              <div class="flex-1">
                <p class="text-xs text-gray-400">Transportation</p>
                <h3 class="text-base font-semibold text-white">Flight</h3>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-400 group-hover:text-white transition-colors"
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
            </div>
            <p class="text-xs text-gray-500">Transport mode</p>
          </div>

          <!-- Accommodation -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-xl p-4 border border-white/10 hover:border-green-500/30 transition-all duration-300 cursor-pointer group"
          >
            <div class="flex items-center gap-3 mb-2">
              <div
                class="w-10 h-10 rounded-full bg-green-600/80 flex items-center justify-center group-hover:bg-green-500 transition-colors"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 text-white"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
                  />
                </svg>
              </div>
              <div class="flex-1">
                <p class="text-xs text-gray-400">Accommodation</p>
                <h3 class="text-base font-semibold text-white">Hotel</h3>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-400 group-hover:text-white transition-colors"
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
            </div>
            <p class="text-xs text-gray-500">Stay type</p>
          </div>
        </div>

        <!-- Create Trip Button -->
        <div class="flex justify-center">
          <NuxtLink to="/plan-trip">
            <button
              class="group px-8 py-4 bg-gradient-to-r from-green-600 to-green-500 hover:from-green-500 hover:to-green-400 text-white font-bold rounded-xl shadow-lg shadow-green-500/30 transition-all duration-300 transform hover:scale-105 flex items-center gap-2"
            >
              <span class="text-lg">Create Trip</span>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 transform group-hover:translate-x-1 transition-transform"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M13 7l5 5m0 0l-5 5m5-5H6"
                />
              </svg>
            </button>
          </NuxtLink>
        </div>
      </div>
    </div>

    <!-- Our Services Section -->
    <div
      id="choose-our-service"
      class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#0a0820] to-[#0f1535]"
    >
      <div class="max-w-7xl mx-auto">
        <!-- Section Header -->
        <div class="text-center mb-10 sm:mb-12">
          <h2
            class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3"
          >
            Choose Our Services
          </h2>
          <p class="text-sm sm:text-base text-gray-400 max-w-2xl mx-auto">
            Explore our comprehensive travel services designed to make your
            journey seamless
          </p>
        </div>

        <!-- Services Grid -->
        <div
          class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 sm:gap-5 md:gap-6"
        >
          <!-- Service 1: Currency Exchange -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-yellow-400/50 hover:shadow-xl hover:shadow-yellow-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <defs>
                  <linearGradient
                    id="gold-gradient"
                    x1="0%"
                    y1="0%"
                    x2="100%"
                    y2="100%"
                  >
                    <stop
                      offset="0%"
                      style="stop-color: #ffd700; stop-opacity: 1"
                    />
                    <stop
                      offset="100%"
                      style="stop-color: #ffa500; stop-opacity: 1"
                    />
                  </linearGradient>
                </defs>
                <circle cx="32" cy="32" r="24" fill="url(#gold-gradient)" />
                <circle
                  cx="32"
                  cy="32"
                  r="19"
                  fill="none"
                  stroke="#D4AF37"
                  stroke-width="2"
                />
                <text
                  x="32"
                  y="38"
                  text-anchor="middle"
                  font-size="18"
                  font-weight="bold"
                  fill="#FFF"
                >
                  $
                </text>
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Currency Exchange
            </h3>
          </div>

          <!-- Service 2: Bus Reservation -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-red-400/50 hover:shadow-xl hover:shadow-red-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <rect
                  x="10"
                  y="20"
                  width="44"
                  height="22"
                  rx="3"
                  fill="#DC143C"
                />
                <rect
                  x="10"
                  y="20"
                  width="44"
                  height="5"
                  rx="3"
                  fill="#8B0000"
                />
                <rect
                  x="14"
                  y="27"
                  width="8"
                  height="6"
                  rx="1"
                  fill="#87CEEB"
                />
                <rect
                  x="26"
                  y="27"
                  width="8"
                  height="6"
                  rx="1"
                  fill="#87CEEB"
                />
                <rect
                  x="38"
                  y="27"
                  width="8"
                  height="6"
                  rx="1"
                  fill="#87CEEB"
                />
                <circle cx="20" cy="46" r="3.5" fill="#2C3E50" />
                <circle cx="20" cy="46" r="1.8" fill="#555" />
                <circle cx="44" cy="46" r="3.5" fill="#2C3E50" />
                <circle cx="44" cy="46" r="1.8" fill="#555" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Bus Reservation
            </h3>
          </div>

          <!-- Service 3: Bus Ticket -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-purple-400/50 hover:shadow-xl hover:shadow-purple-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <defs>
                  <linearGradient
                    id="ticket-gradient"
                    x1="0%"
                    y1="0%"
                    x2="100%"
                    y2="100%"
                  >
                    <stop
                      offset="0%"
                      style="stop-color: #9b59b6; stop-opacity: 1"
                    />
                    <stop
                      offset="100%"
                      style="stop-color: #8e44ad; stop-opacity: 1"
                    />
                  </linearGradient>
                </defs>
                <rect
                  x="20"
                  y="16"
                  width="24"
                  height="32"
                  rx="2"
                  fill="url(#ticket-gradient)"
                />
                <circle cx="20" cy="32" r="2.5" fill="#0a0820" />
                <circle cx="44" cy="32" r="2.5" fill="#0a0820" />
                <rect x="24" y="22" width="16" height="8" rx="1" fill="#FFF" />
                <rect x="24" y="34" width="8" height="1.5" fill="#FFF" />
                <rect x="24" y="37" width="12" height="1.5" fill="#FFF" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Bus Ticket
            </h3>
          </div>

          <!-- Service 4: Train Booking -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-orange-400/50 hover:shadow-xl hover:shadow-orange-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <rect
                  x="16"
                  y="20"
                  width="32"
                  height="20"
                  rx="3"
                  fill="#C0392B"
                />
                <rect
                  x="16"
                  y="20"
                  width="32"
                  height="4"
                  rx="3"
                  fill="#8B0000"
                />
                <rect
                  x="20"
                  y="27"
                  width="8"
                  height="7"
                  rx="1"
                  fill="#ADD8E6"
                />
                <rect
                  x="31"
                  y="27"
                  width="8"
                  height="7"
                  rx="1"
                  fill="#ADD8E6"
                />
                <circle cx="24" cy="44" r="2.5" fill="#2C3E50" />
                <circle cx="40" cy="44" r="2.5" fill="#2C3E50" />
                <rect
                  x="29"
                  y="15"
                  width="6"
                  height="5"
                  rx="1"
                  fill="#FFD700"
                />
                <path d="M30 15 L32 11 L34 15" fill="#FFD700" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Train Booking
            </h3>
          </div>

          <!-- Service 5: Cruise Ship -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-blue-400/50 hover:shadow-xl hover:shadow-blue-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <path
                  d="M12 40 L32 32 L52 40 L49 43 L32 36 L15 43 Z"
                  fill="#2C3E50"
                />
                <rect
                  x="27"
                  y="24"
                  width="10"
                  height="12"
                  rx="1"
                  fill="#E74C3C"
                />
                <rect
                  x="28"
                  y="17"
                  width="8"
                  height="7"
                  rx="1"
                  fill="#1E90FF"
                />
                <rect
                  x="29"
                  y="27"
                  width="2.5"
                  height="3"
                  rx="0.5"
                  fill="#FFF"
                />
                <rect
                  x="33"
                  y="27"
                  width="2.5"
                  height="3"
                  rx="0.5"
                  fill="#FFF"
                />
                <rect
                  x="29"
                  y="31"
                  width="2.5"
                  height="3"
                  rx="0.5"
                  fill="#FFF"
                />
                <rect
                  x="33"
                  y="31"
                  width="2.5"
                  height="3"
                  rx="0.5"
                  fill="#FFF"
                />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Cruise Ship
            </h3>
          </div>

          <!-- Service 6: Travel Insurance -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-teal-400/50 hover:shadow-xl hover:shadow-teal-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <path
                  d="M32 10 L22 16 L22 30 C22 38 27 44 32 48 C37 44 42 38 42 30 L42 16 Z"
                  fill="#20B2AA"
                />
                <path
                  d="M32 14 L25 18 L25 29 C25 35 29 39 32 42 C35 39 39 35 39 29 L39 18 Z"
                  fill="#48D1CC"
                />
                <path
                  d="M28 28 L30 30 L36 24"
                  stroke="#FFF"
                  stroke-width="2"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Travel Insurance
            </h3>
          </div>

          <!-- Service 7: Visa Services -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-indigo-400/50 hover:shadow-xl hover:shadow-indigo-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <defs>
                  <linearGradient
                    id="passport-gradient"
                    x1="0%"
                    y1="0%"
                    x2="100%"
                    y2="100%"
                  >
                    <stop
                      offset="0%"
                      style="stop-color: #5dade2; stop-opacity: 1"
                    />
                    <stop
                      offset="100%"
                      style="stop-color: #3498db; stop-opacity: 1"
                    />
                  </linearGradient>
                </defs>
                <rect
                  x="20"
                  y="14"
                  width="24"
                  height="36"
                  rx="2"
                  fill="url(#passport-gradient)"
                />
                <circle cx="32" cy="26" r="5" fill="#FFF" />
                <rect x="25" y="34" width="14" height="2" fill="#FFF" />
                <rect x="26" y="38" width="12" height="1.5" fill="#FFF" />
                <rect x="26" y="41" width="10" height="1.5" fill="#FFF" />
                <path d="M32 10 L28 14 L36 14 Z" fill="#FFD700" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Visa Services
            </h3>
          </div>

          <!-- Service 8: Work Visa -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-cyan-400/50 hover:shadow-xl hover:shadow-cyan-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <rect
                  x="18"
                  y="20"
                  width="28"
                  height="24"
                  rx="2"
                  fill="#16A085"
                />
                <rect
                  x="18"
                  y="20"
                  width="28"
                  height="5"
                  rx="2"
                  fill="#0E6655"
                />
                <circle cx="26" cy="30" r="3" fill="#FFF" />
                <rect x="32" y="28" width="10" height="1.5" fill="#FFF" />
                <rect x="32" y="31" width="8" height="1.5" fill="#FFF" />
                <rect x="22" y="36" width="20" height="1.5" fill="#FFF" />
                <rect x="22" y="39" width="16" height="1.5" fill="#FFF" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Work Visa
            </h3>
          </div>

          <!-- Service 9: Medical Tourism -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-pink-400/50 hover:shadow-xl hover:shadow-pink-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <circle cx="32" cy="32" r="20" fill="#E74C3C" />
                <rect x="29" y="20" width="6" height="24" rx="1" fill="#FFF" />
                <rect x="20" y="29" width="24" height="6" rx="1" fill="#FFF" />
                <path d="M32 10 L26 16 L38 16 Z" fill="#FFD700" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Medical Tourism
            </h3>
          </div>

          <!-- Service 10: Car Rental -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-green-400/50 hover:shadow-xl hover:shadow-green-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <defs>
                  <linearGradient
                    id="car-gradient"
                    x1="0%"
                    y1="0%"
                    x2="100%"
                    y2="0%"
                  >
                    <stop
                      offset="0%"
                      style="stop-color: #3498db; stop-opacity: 1"
                    />
                    <stop
                      offset="100%"
                      style="stop-color: #2980b9; stop-opacity: 1"
                    />
                  </linearGradient>
                </defs>
                <path
                  d="M14 30 L18 24 L46 24 L50 30 L50 38 L14 38 Z"
                  fill="url(#car-gradient)"
                />
                <rect
                  x="20"
                  y="26"
                  width="7"
                  height="5"
                  rx="1"
                  fill="#87CEEB"
                />
                <rect
                  x="37"
                  y="26"
                  width="7"
                  height="5"
                  rx="1"
                  fill="#87CEEB"
                />
                <circle cx="22" cy="42" r="3" fill="#2C3E50" />
                <circle cx="22" cy="42" r="1.5" fill="#555" />
                <circle cx="42" cy="42" r="3" fill="#2C3E50" />
                <circle cx="42" cy="42" r="1.5" fill="#555" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Car Rental
            </h3>
          </div>

          <!-- Service 11: Flight Tickets -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-yellow-400/50 hover:shadow-xl hover:shadow-yellow-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <defs>
                  <linearGradient
                    id="plane-gradient"
                    x1="0%"
                    y1="0%"
                    x2="100%"
                    y2="100%"
                  >
                    <stop
                      offset="0%"
                      style="stop-color: #3498db; stop-opacity: 1"
                    />
                    <stop
                      offset="100%"
                      style="stop-color: #2980b9; stop-opacity: 1"
                    />
                  </linearGradient>
                </defs>
                <path
                  d="M48 24 L32 20 L16 24 L20 32 L32 36 L44 32 Z"
                  fill="url(#plane-gradient)"
                />
                <rect
                  x="30"
                  y="14"
                  width="4"
                  height="12"
                  fill="url(#plane-gradient)"
                />
                <path d="M28 20 L32 12 L36 20" fill="#FFF" />
                <circle cx="24" cy="28" r="2" fill="#FFF" />
                <circle cx="32" cy="28" r="2" fill="#FFF" />
                <circle cx="40" cy="28" r="2" fill="#FFF" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Flight Tickets
            </h3>
          </div>

          <!-- Service 12: Visa Consulting -->
          <div
            class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:border-red-400/50 hover:shadow-xl hover:shadow-red-500/20 transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          >
            <div
              class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-12 h-12"
                viewBox="0 0 64 64"
              >
                <defs>
                  <linearGradient
                    id="person-gradient"
                    x1="0%"
                    y1="0%"
                    x2="0%"
                    y2="100%"
                  >
                    <stop
                      offset="0%"
                      style="stop-color: #f39c12; stop-opacity: 1"
                    />
                    <stop
                      offset="100%"
                      style="stop-color: #e67e22; stop-opacity: 1"
                    />
                  </linearGradient>
                </defs>
                <circle cx="32" cy="22" r="7" fill="url(#person-gradient)" />
                <path
                  d="M22 36 C22 32 26 30 32 30 C38 30 42 32 42 36 L42 44 L22 44 Z"
                  fill="#3498DB"
                />
                <rect
                  x="28"
                  y="16"
                  width="8"
                  height="3"
                  rx="1.5"
                  fill="#E74C3C"
                />
                <circle cx="26" cy="40" r="1" fill="#FFF" />
                <circle cx="32" cy="40" r="1" fill="#FFF" />
                <circle cx="38" cy="40" r="1" fill="#FFF" />
              </svg>
            </div>
            <h3
              class="text-sm sm:text-base font-semibold text-white text-center"
            >
              Visa Consulting
            </h3>
          </div>
        </div>
      </div>
    </div>

    <!-- Features Section -->
    <div
      id="why-choose-us"
      class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8"
    >
      <div class="max-w-7xl mx-auto">
        <!-- Section Header -->
        <div class="text-center mb-10 sm:mb-12 lg:mb-16">
          <h2
            class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-3 sm:mb-4 px-4"
          >
            Why Choose AI Trip Planner?
          </h2>
          <p class="text-base sm:text-lg text-gray-300 max-w-2xl mx-auto px-4">
            Experience the future of travel planning with our AI-powered
            platform
          </p>
        </div>

        <!-- Features Grid -->
        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5 sm:gap-6 lg:gap-8"
        >
          <!-- Feature 1 -->
          <div
            class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-cyan-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <div
              class="w-12 h-12 sm:w-16 sm:h-16 bg-gradient-to-br from-cyan-400 to-blue-500 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            >
              <span class="text-2xl sm:text-3xl">✈️</span>
            </div>
            <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
              Smart Destinations
            </h3>
            <p class="text-sm sm:text-base text-gray-300">
              AI-powered destination recommendations tailored to your
              preferences and budget
            </p>
          </div>

          <!-- Feature 2 -->
          <div
            class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-purple-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <div
              class="w-12 h-12 sm:w-16 sm:h-16 bg-gradient-to-br from-purple-400 to-pink-500 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            >
              <span class="text-2xl sm:text-3xl">📅</span>
            </div>
            <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
              Itinerary Planning
            </h3>
            <p class="text-sm sm:text-base text-gray-300">
              Personalized day-by-day schedules with optimal routes and timings
            </p>
          </div>

          <!-- Feature 3 -->
          <div
            class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-green-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <div
              class="w-12 h-12 sm:w-16 sm:h-16 bg-gradient-to-br from-green-400 to-emerald-500 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            >
              <span class="text-2xl sm:text-3xl">💰</span>
            </div>
            <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
              Budget Optimization
            </h3>
            <p class="text-sm sm:text-base text-gray-300">
              Get the most value from your trip with smart cost-saving
              suggestions
            </p>
          </div>

          <!-- Feature 4 -->
          <div
            class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-yellow-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <div
              class="w-12 h-12 sm:w-16 sm:h-16 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            >
              <span class="text-2xl sm:text-3xl">🏨</span>
            </div>
            <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
              Hotel Booking
            </h3>
            <p class="text-sm sm:text-base text-gray-300">
              Find and book the perfect accommodation for your stay
            </p>
          </div>

          <!-- Feature 5 -->
          <div
            class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-red-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <div
              class="w-12 h-12 sm:w-16 sm:h-16 bg-gradient-to-br from-red-400 to-pink-500 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            >
              <span class="text-2xl sm:text-3xl">🗺️</span>
            </div>
            <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
              Interactive Maps
            </h3>
            <p class="text-sm sm:text-base text-gray-300">
              Explore destinations with detailed interactive world maps
            </p>
          </div>

          <!-- Feature 6 -->
          <div
            class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-indigo-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <div
              class="w-12 h-12 sm:w-16 sm:h-16 bg-gradient-to-br from-indigo-400 to-purple-500 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            >
              <span class="text-2xl sm:text-3xl">📊</span>
            </div>
            <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
              Travel Analytics
            </h3>
            <p class="text-sm sm:text-base text-gray-300">
              Track your travel history and get personalized insights
            </p>
          </div>
        </div>
      </div>
    </div>

    <!-- Guest Reviews Section -->
    <div
      id="guest-reviews"
      class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#0a0820] to-[#0f1535]"
    >
      <div class="max-w-7xl mx-auto">
        <!-- Section Header -->
        <div class="text-center mb-10 sm:mb-12">
          <h2
            class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3"
          >
            What Our Travelers Say
          </h2>
          <p class="text-sm sm:text-base text-gray-400 max-w-2xl mx-auto">
            Read authentic reviews from thousands of happy travelers who've
            experienced our AI-powered trip planning
          </p>
        </div>

        <!-- Reviews Grid -->
        <div
          class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8"
        >
          <!-- Review 1 -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-cyan-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <!-- Rating -->
            <div class="flex items-center gap-1 mb-4">
              <svg
                v-for="i in 5"
                :key="i"
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-yellow-400"
                viewBox="0 0 20 20"
                fill="currentColor"
              >
                <path
                  d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                />
              </svg>
            </div>

            <!-- Review Text -->
            <p class="text-gray-300 text-sm sm:text-base mb-6 leading-relaxed">
              "AI Trip Planner made my European vacation absolutely seamless!
              The itinerary was perfectly tailored to my interests and budget.
              Highly recommended!"
            </p>

            <!-- Reviewer Info -->
            <div class="flex items-center gap-4">
              <div
                class="w-12 h-12 rounded-full bg-gradient-to-br from-cyan-400 to-blue-600 flex items-center justify-center text-white font-bold text-lg"
              >
                SM
              </div>
              <div>
                <h4 class="text-white font-semibold">Sarah Mitchell</h4>
                <p class="text-gray-400 text-xs">Traveled to Paris, France</p>
              </div>
            </div>
          </div>

          <!-- Review 2 -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-purple-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <!-- Rating -->
            <div class="flex items-center gap-1 mb-4">
              <svg
                v-for="i in 5"
                :key="i"
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-yellow-400"
                viewBox="0 0 20 20"
                fill="currentColor"
              >
                <path
                  d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                />
              </svg>
            </div>

            <!-- Review Text -->
            <p class="text-gray-300 text-sm sm:text-base mb-6 leading-relaxed">
              "The AI suggestions were spot-on! Found hidden gems I wouldn't
              have discovered otherwise. The trip planning process was
              effortless and fun."
            </p>

            <!-- Reviewer Info -->
            <div class="flex items-center gap-4">
              <div
                class="w-12 h-12 rounded-full bg-gradient-to-br from-purple-400 to-pink-600 flex items-center justify-center text-white font-bold text-lg"
              >
                JC
              </div>
              <div>
                <h4 class="text-white font-semibold">James Chen</h4>
                <p class="text-gray-400 text-xs">Traveled to Tokyo, Japan</p>
              </div>
            </div>
          </div>

          <!-- Review 3 -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 sm:p-8 border border-white/10 hover:border-green-400/50 transition-all duration-300 transform hover:-translate-y-2"
          >
            <!-- Rating -->
            <div class="flex items-center gap-1 mb-4">
              <svg
                v-for="i in 5"
                :key="i"
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-yellow-400"
                viewBox="0 0 20 20"
                fill="currentColor"
              >
                <path
                  d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                />
              </svg>
            </div>

            <!-- Review Text -->
            <p class="text-gray-300 text-sm sm:text-base mb-6 leading-relaxed">
              "Best travel planning tool I've used! Saved me hours of research.
              The personalized recommendations were exactly what I was looking
              for."
            </p>

            <!-- Reviewer Info -->
            <div class="flex items-center gap-4">
              <div
                class="w-12 h-12 rounded-full bg-gradient-to-br from-green-400 to-emerald-600 flex items-center justify-center text-white font-bold text-lg"
              >
                ER
              </div>
              <div>
                <h4 class="text-white font-semibold">Emily Rodriguez</h4>
                <p class="text-gray-400 text-xs">Traveled to Bali, Indonesia</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Call to Action Section -->
    <div
      class="py-16 sm:py-20 lg:py-24 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#0f1535] to-[#0a0820] relative overflow-hidden"
    >
      <!-- Background decoration -->
      <div class="absolute inset-0 opacity-20">
        <div
          class="absolute top-20 left-10 w-72 h-72 bg-purple-500 rounded-full filter blur-3xl"
        ></div>
        <div
          class="absolute bottom-20 right-10 w-96 h-96 bg-cyan-500 rounded-full filter blur-3xl"
        ></div>
      </div>

      <div class="max-w-6xl mx-auto relative z-10">
        <div
          class="backdrop-blur-xl bg-white/5 rounded-3xl p-8 sm:p-12 lg:p-16 border border-white/10 shadow-2xl"
        >
          <div class="text-center max-w-3xl mx-auto">
            <h2
              class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-white mb-4 sm:mb-6"
            >
              Ready to Start Your
              <span
                class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-purple-400 to-pink-400"
              >
                Dream Journey?
              </span>
            </h2>
            <p
              class="text-base sm:text-lg md:text-xl text-gray-300 mb-8 sm:mb-10 leading-relaxed"
            >
              Join thousands of travelers who trust AI Trip Planner to create
              unforgettable experiences. Let our AI craft your perfect itinerary
              today!
            </p>

            <!-- CTA Buttons -->
            <div
              class="flex flex-col sm:flex-row gap-4 justify-center items-center"
            >
              <NuxtLink to="/plan-trip">
                <button
                  class="group px-8 py-4 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold rounded-full shadow-lg shadow-cyan-500/30 hover:shadow-xl hover:shadow-cyan-500/50 transition-all duration-300 transform hover:scale-105 flex items-center gap-2"
                >
                  <span class="text-lg">Start Planning Now</span>
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 transform group-hover:translate-x-1 transition-transform"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M13 7l5 5m0 0l-5 5m5-5H6"
                    />
                  </svg>
                </button>
              </NuxtLink>

              <button
                class="px-8 py-4 bg-white/10 hover:bg-white/20 text-white font-semibold rounded-full border-2 border-white/30 hover:border-white/50 transition-all duration-300 transform hover:scale-105"
              >
                Learn More
              </button>
            </div>

            <!-- Stats -->
            <div class="grid grid-cols-3 gap-6 sm:gap-8 mt-12 sm:mt-16">
              <div class="text-center">
                <div
                  class="text-2xl sm:text-3xl md:text-4xl font-bold text-white mb-2"
                >
                  50K+
                </div>
                <div class="text-xs sm:text-sm text-gray-400">
                  Happy Travelers
                </div>
              </div>
              <div class="text-center border-x border-white/20">
                <div
                  class="text-2xl sm:text-3xl md:text-4xl font-bold text-white mb-2"
                >
                  200+
                </div>
                <div class="text-xs sm:text-sm text-gray-400">Destinations</div>
              </div>
              <div class="text-center">
                <div
                  class="text-2xl sm:text-3xl md:text-4xl font-bold text-white mb-2"
                >
                  4.9★
                </div>
                <div class="text-xs sm:text-sm text-gray-400">User Rating</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Contact Us Section -->
    <div
      id="contact"
      class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#0a0820] to-[#0f1535]"
    >
      <div class="max-w-7xl mx-auto">
        <!-- Section Header -->
        <div class="text-center mb-10 sm:mb-12">
          <h2
            class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3"
          >
            Contact
            <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-purple-400 to-pink-400"
            >
              Us
            </span>
          </h2>
          <p class="text-sm sm:text-base text-gray-400 max-w-2xl mx-auto">
            Have questions or need assistance? We're here to help you plan your
            perfect trip
          </p>
        </div>

        <!-- Contact Grid -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-10">
          <!-- Contact Form -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 sm:p-8 border border-white/10 shadow-2xl"
          >
            <h3 class="text-2xl font-bold text-white mb-6">
              Send us a Message
            </h3>
            <form @submit.prevent="handleContactSubmit" class="space-y-5">
              <!-- Name -->
              <div>
                <label class="block text-white font-semibold mb-2 text-sm">
                  Your Name
                </label>
                <input
                  v-model="contactForm.name"
                  type="text"
                  required
                  placeholder="John Doe"
                  class="w-full px-4 py-3 bg-white/10 border border-white/20 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent text-white placeholder-gray-400 transition-all"
                />
              </div>

              <!-- Email -->
              <div>
                <label class="block text-white font-semibold mb-2 text-sm">
                  Email Address
                </label>
                <input
                  v-model="contactForm.email"
                  type="email"
                  required
                  placeholder="john@example.com"
                  class="w-full px-4 py-3 bg-white/10 border border-white/20 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent text-white placeholder-gray-400 transition-all"
                />
              </div>

              <!-- Message -->
              <div>
                <label class="block text-white font-semibold mb-2 text-sm">
                  Message
                </label>
                <textarea
                  v-model="contactForm.message"
                  required
                  rows="4"
                  placeholder="Tell us how we can help you..."
                  class="w-full px-4 py-3 bg-white/10 border border-white/20 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent text-white placeholder-gray-400 transition-all resize-none"
                ></textarea>
              </div>

              <!-- Submit Button -->
              <button
                type="submit"
                class="w-full py-4 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold rounded-xl shadow-lg shadow-cyan-500/30 hover:shadow-xl hover:shadow-cyan-500/50 transition-all duration-300 transform hover:scale-105"
              >
                Send Message
              </button>
            </form>
          </div>

          <!-- Contact Information -->
          <div class="space-y-5">
            <!-- Email Card -->
            <div
              class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 border border-white/10 hover:border-cyan-400/50 transition-all duration-300 group"
            >
              <div class="flex items-start gap-4">
                <div
                  class="w-12 h-12 bg-gradient-to-br from-cyan-400 to-blue-600 rounded-xl flex items-center justify-center flex-shrink-0 group-hover:scale-110 transition-transform duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6 text-white"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                    />
                  </svg>
                </div>
                <div>
                  <h4 class="text-lg font-bold text-white mb-2">Email Us</h4>
                  <p class="text-gray-300 text-sm mb-1">
                    support@aitripplanner.com
                  </p>
                  <p class="text-gray-300 text-sm">info@aitripplanner.com</p>
                </div>
              </div>
            </div>

            <!-- Phone Card -->
            <div
              class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 border border-white/10 hover:border-purple-400/50 transition-all duration-300 group"
            >
              <div class="flex items-start gap-4">
                <div
                  class="w-12 h-12 bg-gradient-to-br from-purple-400 to-pink-600 rounded-xl flex items-center justify-center flex-shrink-0 group-hover:scale-110 transition-transform duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6 text-white"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
                    />
                  </svg>
                </div>
                <div>
                  <h4 class="text-lg font-bold text-white mb-2">Call Us</h4>
                  <p class="text-gray-300 text-sm mb-1">+1 (555) 123-4567</p>
                  <p class="text-gray-300 text-sm">Mon-Fri 9am to 6pm EST</p>
                </div>
              </div>
            </div>

            <!-- Address Card -->
            <div
              class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 border border-white/10 hover:border-green-400/50 transition-all duration-300 group"
            >
              <div class="flex items-start gap-4">
                <div
                  class="w-12 h-12 bg-gradient-to-br from-green-400 to-emerald-600 rounded-xl flex items-center justify-center flex-shrink-0 group-hover:scale-110 transition-transform duration-300"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6 text-white"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
                    />
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
                    />
                  </svg>
                </div>
                <div>
                  <h4 class="text-lg font-bold text-white mb-2">Visit Us</h4>
                  <p class="text-gray-300 text-sm mb-1">123 Travel Street</p>
                  <p class="text-gray-300 text-sm">
                    San Francisco, CA 94102, USA
                  </p>
                </div>
              </div>
            </div>

            <!-- Social Media -->
            <div
              class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 border border-white/10"
            >
              <h4 class="text-lg font-bold text-white mb-4">Connect With Us</h4>
              <div class="flex gap-3">
                <a
                  href="#"
                  class="w-10 h-10 bg-white/10 hover:bg-cyan-500 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110"
                >
                  <svg
                    class="w-5 h-5 text-white"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
                    />
                  </svg>
                </a>
                <a
                  href="#"
                  class="w-10 h-10 bg-white/10 hover:bg-blue-400 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110"
                >
                  <svg
                    class="w-5 h-5 text-white"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"
                    />
                  </svg>
                </a>
                <a
                  href="#"
                  class="w-10 h-10 bg-white/10 hover:bg-pink-500 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110"
                >
                  <svg
                    class="w-5 h-5 text-white"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.899 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.899-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z"
                    />
                  </svg>
                </a>
                <a
                  href="#"
                  class="w-10 h-10 bg-white/10 hover:bg-blue-600 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110"
                >
                  <svg
                    class="w-5 h-5 text-white"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
                    />
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer Section -->
    <footer class="bg-gradient-to-b from-[#0a0820] to-[#050410] text-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 sm:py-16">
        <!-- Main Footer Content -->
        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 sm:gap-10 mb-10"
        >
          <!-- Company Info -->
          <div class="col-span-1 sm:col-span-2 lg:col-span-1">
            <div class="flex items-center gap-2 mb-4">
              <div
                class="w-10 h-10 bg-gradient-to-r from-cyan-500 to-blue-600 rounded-lg flex items-center justify-center"
              >
                <span class="text-2xl">✈️</span>
              </div>
              <h3 class="text-xl font-bold">AI Trip Planner</h3>
            </div>
            <p class="text-gray-400 text-sm mb-4 leading-relaxed">
              Your intelligent travel companion. Plan, explore, and experience
              the world with AI-powered itineraries.
            </p>
            <!-- Social Links -->
            <div class="flex gap-3">
              <a
                href="#"
                class="w-9 h-9 bg-white/5 hover:bg-white/10 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110 border border-white/10 hover:border-cyan-500/50"
              >
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
                  />
                </svg>
              </a>
              <a
                href="#"
                class="w-9 h-9 bg-white/5 hover:bg-white/10 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110 border border-white/10 hover:border-cyan-500/50"
              >
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"
                  />
                </svg>
              </a>
              <a
                href="#"
                class="w-9 h-9 bg-white/5 hover:bg-white/10 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110 border border-white/10 hover:border-cyan-500/50"
              >
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.899 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.899-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z"
                  />
                </svg>
              </a>
              <a
                href="#"
                class="w-9 h-9 bg-white/5 hover:bg-white/10 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110 border border-white/10 hover:border-cyan-500/50"
              >
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
                  />
                </svg>
              </a>
            </div>
          </div>

          <!-- Quick Links -->
          <div>
            <h4 class="text-lg font-semibold mb-4">Quick Links</h4>
            <ul class="space-y-2">
              <li>
                <NuxtLink
                  to="/"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Home
                </NuxtLink>
              </li>
              <li>
                <NuxtLink
                  to="/plan-trip"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Plan Trip
                </NuxtLink>
              </li>
              <li>
                <a
                  href="#statistics"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Statistics
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  About Us
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Contact
                </a>
              </li>
            </ul>
          </div>

          <!-- Services -->
          <div>
            <h4 class="text-lg font-semibold mb-4">Our Services</h4>
            <ul class="space-y-2">
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  AI Trip Planning
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Hotel Booking
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Flight Tickets
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Travel Insurance
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Visa Services
                </a>
              </li>
            </ul>
          </div>

          <!-- Support -->
          <div>
            <h4 class="text-lg font-semibold mb-4">Support</h4>
            <ul class="space-y-2">
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Help Center
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Privacy Policy
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Terms of Service
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  FAQ
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
                >
                  Contact Support
                </a>
              </li>
            </ul>
          </div>
        </div>

        <!-- Bottom Bar -->
        <div
          class="pt-8 border-t border-white/10 flex flex-col sm:flex-row justify-between items-center gap-4"
        >
          <p class="text-gray-400 text-sm text-center sm:text-left">
            © 2025 AI Trip Planner. All rights reserved.
          </p>
          <div class="flex gap-6">
            <a
              href="#"
              class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
            >
              Privacy
            </a>
            <a
              href="#"
              class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
            >
              Terms
            </a>
            <a
              href="#"
              class="text-gray-400 hover:text-cyan-400 text-sm transition-colors duration-300"
            >
              Cookies
            </a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";

// Navigation state
// Default to none; buttons highlight only when their route matches
const activeNav = ref("hero");
const showMobileMenu = ref(false);
const showCountryDropdown = ref(false);
const showAboutDropdown = ref(false);
const countrySearch = ref("");
const countryFilter = ref("popular");

// Countries list with flags
const countries = ref([
  { name: "United States", code: "US", flag: "🇺🇸" },
  { name: "United Kingdom", code: "GB", flag: "🇬🇧" },
  { name: "Canada", code: "CA", flag: "🇨🇦" },
  { name: "Australia", code: "AU", flag: "🇦🇺" },
  { name: "Germany", code: "DE", flag: "🇩🇪" },
  { name: "France", code: "FR", flag: "🇫🇷" },
  { name: "Spain", code: "ES", flag: "🇪🇸" },
  { name: "Italy", code: "IT", flag: "🇮🇹" },
  { name: "Japan", code: "JP", flag: "🇯🇵" },
  { name: "China", code: "CN", flag: "🇨🇳" },
  { name: "India", code: "IN", flag: "🇮🇳" },
  { name: "Brazil", code: "BR", flag: "🇧🇷" },
  { name: "Mexico", code: "MX", flag: "🇲🇽" },
  { name: "South Korea", code: "KR", flag: "🇰🇷" },
  { name: "Netherlands", code: "NL", flag: "🇳🇱" },
  { name: "Switzerland", code: "CH", flag: "🇨🇭" },
  { name: "Sweden", code: "SE", flag: "🇸🇪" },
  { name: "Norway", code: "NO", flag: "🇳🇴" },
  { name: "Denmark", code: "DK", flag: "🇩🇰" },
  { name: "Finland", code: "FI", flag: "🇫🇮" },
  { name: "Belgium", code: "BE", flag: "🇧🇪" },
  { name: "Austria", code: "AT", flag: "🇦🇹" },
  { name: "Poland", code: "PL", flag: "🇵🇱" },
  { name: "Greece", code: "GR", flag: "🇬🇷" },
  { name: "Portugal", code: "PT", flag: "🇵🇹" },
  { name: "Turkey", code: "TR", flag: "🇹🇷" },
  { name: "United Arab Emirates", code: "AE", flag: "🇦🇪" },
  { name: "Saudi Arabia", code: "SA", flag: "🇸🇦" },
  { name: "Singapore", code: "SG", flag: "🇸🇬" },
  { name: "Malaysia", code: "MY", flag: "🇲🇾" },
  { name: "Thailand", code: "TH", flag: "🇹🇭" },
  { name: "Indonesia", code: "ID", flag: "🇮🇩" },
  { name: "Philippines", code: "PH", flag: "🇵🇭" },
  { name: "Vietnam", code: "VN", flag: "🇻🇳" },
  { name: "New Zealand", code: "NZ", flag: "🇳🇿" },
  { name: "Argentina", code: "AR", flag: "🇦🇷" },
  { name: "Chile", code: "CL", flag: "🇨🇱" },
  { name: "Colombia", code: "CO", flag: "🇨🇴" },
  { name: "Peru", code: "PE", flag: "🇵🇪" },
  { name: "South Africa", code: "ZA", flag: "🇿🇦" },
  { name: "Egypt", code: "EG", flag: "🇪🇬" },
  { name: "Morocco", code: "MA", flag: "🇲🇦" },
  { name: "Kenya", code: "KE", flag: "🇰🇪" },
  { name: "Nigeria", code: "NG", flag: "🇳🇬" },
  { name: "Russia", code: "RU", flag: "🇷🇺" },
  { name: "Ukraine", code: "UA", flag: "🇺🇦" },
  { name: "Czech Republic", code: "CZ", flag: "🇨🇿" },
  { name: "Hungary", code: "HU", flag: "🇭🇺" },
  { name: "Romania", code: "RO", flag: "🇷🇴" },
  { name: "Ireland", code: "IE", flag: "🇮🇪" },
  { name: "Iceland", code: "IS", flag: "🇮🇸" },
  { name: "Croatia", code: "HR", flag: "🇭🇷" },
  { name: "Bangladesh", code: "BD", flag: "🇧🇩" },
  { name: "Pakistan", code: "PK", flag: "🇵🇰" },
  { name: "Sri Lanka", code: "LK", flag: "🇱🇰" },
  { name: "Israel", code: "IL", flag: "🇮🇱" },
  { name: "Qatar", code: "QA", flag: "🇶🇦" },
  { name: "Kuwait", code: "KW", flag: "🇰🇼" },
  { name: "Bahrain", code: "BH", flag: "🇧🇭" },
  { name: "Oman", code: "OM", flag: "🇴🇲" },
  { name: "Jordan", code: "JO", flag: "🇯🇴" },
  { name: "Lebanon", code: "LB", flag: "🇱🇧" },
]);

// Popular tourist destination countries
const popularCountryCodes = [
  "FR",
  "ES",
  "US",
  "IT",
  "TR",
  "MX",
  "TH",
  "GB",
  "DE",
  "JP",
  "AT",
  "GR",
  "MY",
  "PT",
  "AE",
  "SA",
  "NL",
  "CH",
  "SG",
  "KR",
  "ID",
  "EG",
  "MA",
  "AU",
  "CA",
  "CN",
  "IN",
  "BR",
  "AR",
  "ZA",
];

// Selected country (default to US)
const selectedCountry = ref(countries.value[0]);

// Filtered countries based on search and filter
const filteredCountries = computed(() => {
  let result = countries.value;

  // Apply popular filter
  if (countryFilter.value === "popular") {
    result = result.filter((country) =>
      popularCountryCodes.includes(country.code)
    );
  }

  // Apply search filter
  if (countrySearch.value) {
    const search = countrySearch.value.toLowerCase();
    result = result.filter(
      (country) =>
        country.name.toLowerCase().includes(search) ||
        country.code.toLowerCase().includes(search)
    );
  }

  return result;
});

// Select country
const selectCountry = (country) => {
  selectedCountry.value = country;
  showCountryDropdown.value = false;
  countrySearch.value = "";
};

// Scroll to any section
const scrollToSection = (sectionId) => {
  if (sectionId === "hero") {
    window.scrollTo({ top: 0, behavior: "smooth" });
    activeNav.value = "hero";
    return;
  }

  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: "smooth", block: "start" });
  }
  activeNav.value = sectionId;
};

// Scroll spy functionality to detect active section
onMounted(() => {
  const handleScroll = () => {
    const sections = [
      { id: "hero", offset: 0 },
      { id: "statistics", element: document.getElementById("statistics") },
      {
        id: "choose-our-service",
        element: document.getElementById("choose-our-service"),
      },
      {
        id: "why-choose-us",
        element: document.getElementById("why-choose-us"),
      },
      {
        id: "guest-reviews",
        element: document.getElementById("guest-reviews"),
      },
      { id: "contact", element: document.getElementById("contact") },
    ];

    const scrollPosition = window.scrollY + 200; // Offset for navbar height

    // Check if at top
    if (window.scrollY < 300) {
      activeNav.value = "hero";
      return;
    }

    // Check each section
    for (let i = sections.length - 1; i >= 0; i--) {
      const section = sections[i];
      if (section.element) {
        const sectionTop = section.element.offsetTop;
        if (scrollPosition >= sectionTop) {
          // Map section IDs to nav items
          if (
            section.id === "choose-our-service" ||
            section.id === "why-choose-us" ||
            section.id === "guest-reviews"
          ) {
            activeNav.value = "about";
          } else {
            activeNav.value = section.id;
          }
          return;
        }
      }
    }
  };

  window.addEventListener("scroll", handleScroll);
  handleScroll(); // Initial call

  // Cleanup
  return () => {
    window.removeEventListener("scroll", handleScroll);
  };
});

// Contact form
const contactForm = ref({
  name: "",
  email: "",
  message: "",
});

const handleContactSubmit = () => {
  alert("Thank you for your message! We'll get back to you soon.");
  // Reset form
  contactForm.value = {
    name: "",
    email: "",
    message: "",
  };
};
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 0.6s ease-out;
}

@keyframes spin-slow {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.animate-spin-slow {
  animation: spin-slow 60s linear infinite;
}

@keyframes dash {
  0% {
    stroke-dashoffset: 100;
  }
  100% {
    stroke-dashoffset: 0;
  }
}

@keyframes dash-slow {
  0% {
    stroke-dashoffset: 120;
  }
  100% {
    stroke-dashoffset: 0;
  }
}

.animate-dash {
  animation: dash 3s linear infinite;
}

.animate-dash-slow {
  animation: dash-slow 4s linear infinite;
}

/* Beautiful Animated Stars Background */
.stars-container {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.stars-layer {
  position: absolute;
  width: 100%;
  height: 100%;
  background-repeat: repeat;
  background-position: center;
}

/* Layer 1 - Small stars */
.stars-layer-1 {
  background-image: radial-gradient(1px 1px at 20px 30px, white, transparent),
    radial-gradient(1px 1px at 60px 70px, white, transparent),
    radial-gradient(1px 1px at 50px 160px, white, transparent),
    radial-gradient(1px 1px at 130px 80px, white, transparent),
    radial-gradient(1px 1px at 140px 150px, white, transparent),
    radial-gradient(1px 1px at 200px 40px, white, transparent),
    radial-gradient(1px 1px at 220px 120px, white, transparent),
    radial-gradient(1px 1px at 280px 90px, white, transparent),
    radial-gradient(1px 1px at 320px 170px, white, transparent),
    radial-gradient(1px 1px at 380px 50px, white, transparent);
  background-size: 400px 200px;
  animation: stars-float-1 80s linear infinite;
  opacity: 0.6;
}

/* Layer 2 - Medium stars */
.stars-layer-2 {
  background-image: radial-gradient(
      1.5px 1.5px at 80px 50px,
      rgba(255, 255, 255, 0.9),
      transparent
    ),
    radial-gradient(
      1.5px 1.5px at 180px 140px,
      rgba(255, 255, 255, 0.9),
      transparent
    ),
    radial-gradient(
      1.5px 1.5px at 250px 80px,
      rgba(255, 255, 255, 0.9),
      transparent
    ),
    radial-gradient(
      1.5px 1.5px at 350px 130px,
      rgba(255, 255, 255, 0.9),
      transparent
    ),
    radial-gradient(
      1.5px 1.5px at 100px 180px,
      rgba(255, 255, 255, 0.9),
      transparent
    ),
    radial-gradient(
      1.5px 1.5px at 300px 20px,
      rgba(255, 255, 255, 0.9),
      transparent
    );
  background-size: 450px 250px;
  animation: stars-float-2 100s linear infinite;
  opacity: 0.5;
}

/* Layer 3 - Large stars with twinkling effect */
.stars-layer-3 {
  background-image: radial-gradient(
      2px 2px at 40px 80px,
      rgba(255, 255, 255, 1),
      transparent
    ),
    radial-gradient(2px 2px at 150px 30px, rgba(255, 255, 255, 1), transparent),
    radial-gradient(2px 2px at 240px 140px, rgba(255, 255, 255, 1), transparent),
    radial-gradient(2px 2px at 330px 60px, rgba(255, 255, 255, 1), transparent),
    radial-gradient(2px 2px at 120px 150px, rgba(255, 255, 255, 1), transparent);
  background-size: 500px 280px;
  animation: stars-float-3 120s linear infinite, twinkle 3s ease-in-out infinite;
  opacity: 0.7;
}

@keyframes stars-float-1 {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-200px);
  }
}

@keyframes stars-float-2 {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-250px);
  }
}

@keyframes stars-float-3 {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-280px);
  }
}

@keyframes twinkle {
  0%,
  100% {
    opacity: 0.7;
  }
  50% {
    opacity: 1;
  }
}
</style>
