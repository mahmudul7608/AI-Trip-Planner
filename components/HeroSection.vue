<template>
  <div id="hero" class="relative min-h-[calc(100vh-72px)] overflow-hidden">
    <!-- Dark Gradient Background -->
    <div
      class="absolute inset-0 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
    ></div>

    <!-- Hero Content -->
    <div
      class="relative z-10 flex items-center min-h-[calc(100vh-72px)] py-12 sm:py-16 lg:py-20"
    >
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-12 xl:px-16 w-full">
        <div
          class="grid grid-cols-1 lg:grid-cols-2 gap-10 lg:gap-16 xl:gap-20 items-center"
        >
          <!-- Left Column - Text Content -->
          <div class="space-y-6 sm:space-y-8">
            <!-- Badge -->
            <div
              class="inline-flex items-center space-x-2 bg-gradient-to-r from-cyan-500/20 to-purple-500/20 px-5 py-2.5 rounded-full border border-cyan-400/30 shadow-lg"
            >
              <span class="text-cyan-300 font-bold text-sm tracking-wide"
                >AI Trip Generator</span
              >
            </div>

            <!-- Main Heading -->
            <h1
              class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-extrabold leading-tight"
            >
              <span class="text-white">Ready to Start Your</span>
              <span
                class="bg-gradient-to-r from-cyan-400 to-blue-500 bg-clip-text text-transparent"
              >
                Dream</span
              >
              <span
                class="bg-gradient-to-r from-purple-400 to-pink-500 bg-clip-text text-transparent"
              >
                Journey?</span
              >
            </h1>

            <!-- Subtitle -->
            <p
              class="text-lg sm:text-xl text-gray-300 leading-relaxed max-w-xl"
            >
              Join thousands of travelers who trust AI Trip Planner to create
              unforgettable experiences. Let our AI craft your perfect itinerary
              today!
            </p>

            <!-- CTA Button -->
            <div class="flex items-start sm:items-center">
              <NuxtLink to="/plan-trip">
                <button
                  class="group px-10 py-4 bg-gradient-to-r from-cyan-500 via-cyan-600 to-blue-600 hover:from-cyan-400 hover:via-cyan-500 hover:to-blue-500 text-white font-bold rounded-full transition-all duration-300 transform hover:scale-105 text-base sm:text-lg flex items-center gap-3"
                >
                  <span>Start Planning Now</span>
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
                      stroke-width="2.5"
                      d="M13 7l5 5m0 0l-5 5m5-5H6"
                    />
                  </svg>
                </button>
              </NuxtLink>
            </div>
          </div>

          <!-- Right Column - Image -->
          <div class="flex items-center justify-center lg:justify-end">
            <div class="relative w-full max-w-sm lg:max-w-md mx-auto">
              <!-- Main Image -->
              <img
                src="/images/Ai-powerd-owl.png"
                alt="AI Powered Trip Planning"
                class="w-full h-auto max-h-[500px] object-contain drop-shadow-2xl"
              />
              <!-- Decorative elements -->
              <div
                class="absolute -top-6 -right-6 w-48 h-48 bg-gradient-to-br from-purple-300/20 to-pink-300/20 rounded-full blur-3xl -z-10"
              ></div>
              <div
                class="absolute -bottom-6 -left-6 w-48 h-48 bg-gradient-to-br from-cyan-300/20 to-blue-300/20 rounded-full blur-3xl -z-10"
              ></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>
