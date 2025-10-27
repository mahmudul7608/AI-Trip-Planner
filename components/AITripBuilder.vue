<template>
  <div
    class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
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
              <h3 class="text-base font-semibold text-white">Paris, France</h3>
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
</template>

<script setup></script>
