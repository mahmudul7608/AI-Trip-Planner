<template>
  <div id="hero" class="relative min-h-[calc(100vh-72px)] overflow-hidden">
    <!-- Dark Gradient Background -->
    <div
      class="absolute inset-0 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
    ></div>

    <!-- Hero Content -->
    <div
      class="relative z-10 flex items-center min-h-[calc(100vh-72px)] py-6 sm:py-10 lg:py-12"
    >
      <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 w-full">
        <div
          class="grid grid-cols-1 lg:grid-cols-2 gap-6 sm:gap-8 lg:gap-12 xl:gap-16 items-center"
        >
          <!-- Left Column - Text Content -->
          <div
            class="space-y-4 sm:space-y-5 lg:space-y-6 text-center lg:text-left"
          >
            <!-- Badge Above Text -->
            <div class="flex justify-center lg:justify-start mb-2">
              <div
                class="inline-flex items-center space-x-1.5 bg-gradient-to-r from-cyan-500/20 via-purple-500/20 to-pink-500/20 px-3 py-1.5 sm:px-4 sm:py-2 rounded-full border border-cyan-400/30 shadow-lg backdrop-blur-sm hover:scale-105 transition-all duration-300 cursor-pointer"
              >
                <span
                  class="inline-flex items-center justify-center px-1.5 py-0.5 text-[8px] sm:text-[9px] font-bold text-purple-600 bg-white rounded-full uppercase tracking-wider"
                >
                  NEW
                </span>
                <span
                  class="text-cyan-300 font-bold text-[10px] sm:text-xs tracking-wide"
                >
                  AI Trip Planner
                </span>
              </div>
            </div>

            <!-- Main Heading -->
            <h1
              class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl xl:text-6xl font-extrabold leading-tight"
            >
              <span class="text-white block sm:inline"
                >Ready to Start Your</span
              >
              <span
                class="bg-gradient-to-r from-cyan-400 to-blue-500 bg-clip-text text-transparent block sm:inline"
              >
                Dream</span
              >
              <span
                class="bg-gradient-to-r from-purple-400 to-pink-500 bg-clip-text text-transparent block sm:inline"
              >
                Journey?</span
              >
            </h1>

            <!-- Subtitle -->
            <p
              class="text-sm sm:text-base lg:text-lg text-gray-300 leading-relaxed max-w-xl mx-auto lg:mx-0"
            >
              Join thousands of travelers who trust AI Trip Planner to create
              unforgettable experiences. Let our AI craft your perfect itinerary
              today!
            </p>

            <!-- CTA Button -->
            <div class="flex items-center justify-center lg:justify-start pt-2">
              <NuxtLink to="/plan-trip">
                <button
                  class="group px-7 sm:px-9 py-3 sm:py-3.5 bg-gradient-to-r from-cyan-500 via-cyan-600 to-blue-600 hover:from-cyan-400 hover:via-cyan-500 hover:to-blue-500 text-white font-bold rounded-full transition-all duration-300 transform hover:scale-105 text-sm sm:text-base flex items-center gap-2"
                >
                  <span>Start Planning Now</span>
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-4 w-4 sm:h-5 sm:w-5 transform group-hover:translate-x-1 transition-transform"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2.5"
                      d="M13 7l5 5m0 0l-5 5m5-5H6"
                    />
                  </svg>
                </button>
              </NuxtLink>
            </div>
          </div>

          <!-- Right Column - Image -->
          <div
            class="flex items-center justify-center lg:justify-end mt-6 lg:mt-0"
          >
            <div
              class="relative w-full max-w-[250px] sm:max-w-[300px] md:max-w-sm lg:max-w-md mx-auto lg:mx-0"
            >
              <!-- Main Image -->
              <img
                src="/images/Ai-powerd-owl.png"
                alt="AI Powered Trip Planning"
                class="w-full h-auto max-h-[300px] sm:max-h-[360px] md:max-h-[420px] lg:max-h-[480px] object-contain drop-shadow-2xl animate-float"
              />
              <!-- Decorative elements -->
              <div
                class="absolute -top-4 -right-4 w-28 h-28 sm:w-32 sm:h-32 md:w-36 md:h-36 lg:w-40 lg:h-40 bg-gradient-to-br from-purple-300/20 to-pink-300/20 rounded-full blur-3xl -z-10"
              ></div>
              <div
                class="absolute -bottom-4 -left-4 w-28 h-28 sm:w-32 sm:h-32 md:w-36 md:h-36 lg:w-40 lg:h-40 bg-gradient-to-br from-cyan-300/20 to-blue-300/20 rounded-full blur-3xl -z-10"
              ></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>
