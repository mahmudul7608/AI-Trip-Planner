<template>
  <div
    id="statistics"
    class="py-8 sm:py-12 lg:py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
  >
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-8 sm:mb-10">
        <h2
          class="text-2xl sm:text-3xl md:text-4xl font-bold text-white mb-2 sm:mb-3"
        >
          Travel Statistics
        </h2>
        <p class="text-sm sm:text-base text-gray-300 max-w-xl mx-auto">
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
                  <p class="text-gray-400 text-xs truncate">Virginia → SAN-B</p>
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
                  <p class="text-blue-400 text-[10px] font-semibold">Arrived</p>
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
                <h3 class="text-base sm:text-lg font-semibold text-white mb-1">
                  Travel activity
                </h3>
                <p class="text-xs text-gray-400">Jane Noor</p>
              </div>

              <!-- 89% Stats -->
              <div class="mt-auto">
                <h2 class="text-5xl sm:text-6xl font-bold text-white mb-2">
                  89%
                </h2>
                <p class="text-xs text-gray-400 leading-relaxed max-w-[200px]">
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
</template>

<script setup></script>
