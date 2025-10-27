<template>
  <div
    class="h-screen overflow-hidden bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
  >
    <!-- Navigation Bar (same as home) -->
    <nav
      class="sticky top-0 z-50 bg-[#1a1f3a]/95 backdrop-blur-md shadow-lg border-b border-cyan-500/20"
    >
      <div class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16 sm:h-20 lg:h-24">
          <!-- Logo -->
          <NuxtLink
            to="/"
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
          </NuxtLink>

          <!-- Back Button -->
          <NuxtLink to="/">
            <button
              class="flex items-center space-x-1 sm:space-x-2 px-3 sm:px-6 py-2 sm:py-3 bg-white/10 hover:bg-gradient-to-r hover:from-cyan-400/30 hover:to-blue-500/30 text-white font-semibold rounded-lg sm:rounded-xl transition-all duration-300 text-sm sm:text-base transform hover:scale-105"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-4 w-4 sm:h-5 sm:w-5"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M10 19l-7-7m0 0l7-7m-7 7h18"
                />
              </svg>
              <span class="hidden sm:inline">Back</span>
            </button>
          </NuxtLink>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <div
      class="relative h-[calc(100vh-4rem)] sm:h-[calc(100vh-5rem)] lg:h-[calc(100vh-6rem)] overflow-y-auto scrollbar-thin"
    >
      <div class="max-w-[1600px] mx-auto px-4 sm:px-6 lg:px-8 py-6 sm:py-8">
        <!-- Header -->
        <div class="text-center mb-6 sm:mb-8">
          <div class="relative inline-block">
            <h1
              class="text-3xl sm:text-4xl md:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 via-blue-400 to-purple-400 mb-2 sm:mb-3 drop-shadow-2xl leading-tight animate-gradient"
            >
              Plan Your Dream Trip
            </h1>
            <div
              class="absolute -inset-1 bg-gradient-to-r from-cyan-500/20 via-blue-500/20 to-purple-500/20 blur-xl rounded-full"
            ></div>
          </div>
          <p class="text-sm sm:text-base text-blue-100/90 px-4 font-light">
            Tell us where you want to go, and AI will create a personalized trip
            plan for you
          </p>
        </div>

        <!-- Two Column Layout: Video Left, Form Right -->
        <div
          class="grid grid-cols-1 lg:grid-cols-2 gap-6 lg:gap-8 items-stretch"
        >
          <!-- Left Side - Video Section -->
          <div
            class="relative backdrop-blur-xl bg-gradient-to-br from-white/[0.12] via-white/[0.08] to-white/[0.05] rounded-3xl shadow-[0_8px_32px_rgba(0,0,0,0.3)] p-5 sm:p-7 border border-white/30 ring-1 ring-white/20 overflow-hidden group"
          >
            <!-- Decorative gradient orbs -->
            <div
              class="absolute top-0 right-0 w-40 h-40 bg-gradient-to-br from-cyan-500/10 to-blue-500/10 rounded-full blur-3xl"
            ></div>
            <div
              class="absolute bottom-0 left-0 w-40 h-40 bg-gradient-to-tr from-purple-500/10 to-pink-500/10 rounded-full blur-3xl"
            ></div>

            <div class="relative z-10 flex flex-col h-full">
              <!-- AI Powered Badge -->
              <div class="flex items-center justify-center mb-3">
                <div
                  class="flex items-center gap-2 bg-gradient-to-r from-cyan-500/20 to-purple-500/20 backdrop-blur-sm px-3 py-1.5 rounded-full border border-cyan-400/30"
                >
                  <img
                    src="/images/Ai-powerd-owl.png"
                    alt="AI Powered"
                    class="w-6 h-6 object-contain"
                  />
                  <span class="text-cyan-300 font-semibold text-xs sm:text-sm">
                    AI Powered Planning
                  </span>
                </div>
              </div>

              <!-- Video Container -->
              <div
                class="relative rounded-2xl overflow-hidden shadow-2xl border-2 border-white/20 group-hover:border-cyan-400/40 transition-all duration-500 mb-4"
              >
                <div
                  class="relative"
                  style="max-height: 280px; overflow: hidden"
                >
                  <video
                    autoplay
                    loop
                    muted
                    playsinline
                    class="w-full h-full object-cover rounded-xl"
                    style="max-height: 280px"
                  >
                    <source src="/images/Ai-tour-plan.mp4" type="video/mp4" />
                    Your browser does not support the video tag.
                  </video>

                  <!-- Video Overlay Gradient -->
                  <div
                    class="absolute inset-0 bg-gradient-to-t from-[#0a0820]/50 via-transparent to-transparent pointer-events-none"
                  ></div>
                </div>
              </div>

              <!-- Features List -->
              <div class="space-y-2 flex-1">
                <div
                  class="flex items-center gap-2.5 text-white bg-white/5 rounded-lg p-2.5 backdrop-blur-sm border border-white/10"
                >
                  <div
                    class="flex-shrink-0 w-9 h-9 bg-gradient-to-br from-cyan-500/20 to-blue-500/20 rounded-lg flex items-center justify-center"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4 text-cyan-400"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M13 10V3L4 14h7v7l9-11h-7z"
                      />
                    </svg>
                  </div>
                  <div>
                    <h4 class="font-semibold text-xs sm:text-sm">
                      Instant AI Generation
                    </h4>
                    <p class="text-[10px] sm:text-xs text-blue-100/70">
                      Personalized itinerary in seconds
                    </p>
                  </div>
                </div>

                <div
                  class="flex items-center gap-2.5 text-white bg-white/5 rounded-lg p-2.5 backdrop-blur-sm border border-white/10"
                >
                  <div
                    class="flex-shrink-0 w-9 h-9 bg-gradient-to-br from-purple-500/20 to-pink-500/20 rounded-lg flex items-center justify-center"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4 text-purple-400"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
                      />
                    </svg>
                  </div>
                  <div>
                    <h4 class="font-semibold text-xs sm:text-sm">
                      Smart Recommendations
                    </h4>
                    <p class="text-[10px] sm:text-xs text-blue-100/70">
                      Hotels, activities & transport
                    </p>
                  </div>
                </div>

                <div
                  class="flex items-center gap-2.5 text-white bg-white/5 rounded-lg p-2.5 backdrop-blur-sm border border-white/10"
                >
                  <div
                    class="flex-shrink-0 w-9 h-9 bg-gradient-to-br from-green-500/20 to-emerald-500/20 rounded-lg flex items-center justify-center"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4 text-green-400"
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
                  <div>
                    <h4 class="font-semibold text-xs sm:text-sm">
                      Budget Optimized
                    </h4>
                    <p class="text-[10px] sm:text-xs text-blue-100/70">
                      Plans tailored to your budget
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Right Side - Trip Form -->
          <div
            class="relative backdrop-blur-xl bg-gradient-to-br from-white/[0.12] via-white/[0.08] to-white/[0.05] rounded-3xl shadow-[0_8px_32px_rgba(0,0,0,0.3)] p-5 sm:p-7 border border-white/30 ring-1 ring-white/20 overflow-hidden flex flex-col"
          >
            <!-- Decorative gradient orbs -->
            <div
              class="absolute top-0 right-0 w-40 h-40 bg-gradient-to-br from-cyan-500/10 to-blue-500/10 rounded-full blur-3xl"
            ></div>
            <div
              class="absolute bottom-0 left-0 w-40 h-40 bg-gradient-to-tr from-purple-500/10 to-pink-500/10 rounded-full blur-3xl"
            ></div>

            <form
              @submit.prevent="generateTripPlan"
              class="relative space-y-3 sm:space-y-4 flex-1 flex flex-col"
            >
              <!-- Destination Input -->
              <div class="group">
                <label
                  class="flex items-center text-white font-semibold mb-2 text-sm sm:text-base"
                >
                  <span
                    class="text-xl mr-2 group-hover:scale-110 transition-transform"
                    >📍</span
                  >
                  <span>Destination</span>
                </label>
                <div class="relative">
                  <input
                    v-model="tripData.destination"
                    type="text"
                    placeholder="e.g., Paris, France"
                    required
                    class="w-full px-4 py-2.5 bg-white/95 border border-cyan-300/50 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:border-transparent text-gray-800 text-sm sm:text-base placeholder-gray-400 transition-all duration-300 hover:border-cyan-400/70 shadow-sm hover:shadow-md"
                  />
                </div>
              </div>

              <!-- Date Range -->
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-4">
                <div class="group">
                  <label
                    class="flex items-center text-white font-semibold mb-2 text-sm"
                  >
                    <span
                      class="text-lg mr-2 group-hover:scale-110 transition-transform"
                      >📅</span
                    >
                    <span>Start Date</span>
                  </label>
                  <input
                    v-model="tripData.startDate"
                    type="date"
                    required
                    class="w-full px-3 py-2 bg-white/95 border border-blue-300/50 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-400 text-gray-800 text-sm transition-all duration-300 hover:border-blue-400/70 shadow-sm hover:shadow-md"
                  />
                </div>
                <div class="group">
                  <label
                    class="flex items-center text-white font-semibold mb-2 text-sm"
                  >
                    <span
                      class="text-lg mr-2 group-hover:scale-110 transition-transform"
                      >📅</span
                    >
                    <span>End Date</span>
                  </label>
                  <input
                    v-model="tripData.endDate"
                    type="date"
                    required
                    class="w-full px-3 py-2 bg-white/95 border border-blue-300/50 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-400 text-gray-800 text-sm transition-all duration-300 hover:border-blue-400/70 shadow-sm hover:shadow-md"
                  />
                </div>
              </div>

              <!-- Budget and Travelers in Grid -->
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-4">
                <!-- Budget -->
                <div class="group">
                  <label
                    class="flex items-center text-white font-semibold mb-2 text-sm sm:text-base"
                  >
                    <span
                      class="text-xl mr-2 group-hover:scale-110 transition-transform"
                      >💰</span
                    >
                    <span>Budget (USD)</span>
                  </label>
                  <input
                    v-model="tripData.budget"
                    type="number"
                    placeholder="Your budget"
                    required
                    class="w-full px-4 py-2.5 bg-white/95 border border-green-300/50 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-400 text-gray-800 text-sm sm:text-base placeholder-gray-400 transition-all duration-300 hover:border-green-400/70 shadow-sm hover:shadow-md"
                  />
                </div>

                <!-- Travelers -->
                <div class="group">
                  <label
                    class="flex items-center text-white font-semibold mb-2 text-sm sm:text-base"
                  >
                    <span
                      class="text-xl mr-2 group-hover:scale-110 transition-transform"
                      >👥</span
                    >
                    <span>Travelers</span>
                  </label>
                  <input
                    v-model="tripData.travelers"
                    type="number"
                    min="1"
                    placeholder="Number"
                    required
                    class="w-full px-4 py-2.5 bg-white/95 border border-purple-300/50 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-400 text-gray-800 text-sm sm:text-base placeholder-gray-400 transition-all duration-300 hover:border-purple-400/70 shadow-sm hover:shadow-md"
                  />
                </div>
              </div>

              <!-- Preferences -->
              <div class="group">
                <label
                  class="flex items-center text-white font-semibold mb-2 text-sm sm:text-base"
                >
                  <span
                    class="text-xl mr-2 group-hover:scale-110 transition-transform"
                    >⭐</span
                  >
                  <span>Travel Preferences</span>
                </label>
                <textarea
                  v-model="tripData.preferences"
                  rows="3"
                  placeholder="Tell us about your interests... (e.g., adventure, culture, food, relaxation)"
                  class="w-full px-4 py-2.5 bg-white/95 border border-pink-300/50 rounded-xl focus:outline-none focus:ring-2 focus:ring-pink-400 text-gray-800 text-sm sm:text-base placeholder-gray-400 resize-none transition-all duration-300 hover:border-pink-400/70 shadow-sm hover:shadow-md"
                >
                </textarea>
              </div>

              <!-- Spacer to push button to bottom -->
              <div class="flex-grow"></div>

              <!-- Submit Button -->
              <button
                type="submit"
                :disabled="isGenerating"
                class="group relative w-full py-3.5 bg-gradient-to-r from-[#FF6B6B] via-[#FF4E9A] to-[#B620E0] hover:from-[#FF5252] hover:via-[#FF3D8F] hover:to-[#A00FD0] text-white font-bold rounded-2xl shadow-[0_8px_32px_rgba(255,78,154,0.5)] hover:shadow-[0_12px_40px_rgba(255,78,154,0.7)] transition-all duration-500 transform hover:scale-[1.02] active:scale-[0.98] text-base sm:text-lg disabled:opacity-50 disabled:cursor-not-allowed overflow-hidden"
              >
                <!-- Animated gradient overlay -->
                <div
                  class="absolute inset-0 bg-gradient-to-r from-[#FF8E8E] via-[#FF6BB5] to-[#D040FF] opacity-0 group-hover:opacity-40 transition-opacity duration-500"
                ></div>

                <!-- Shine effect -->
                <div
                  class="absolute inset-0 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 bg-gradient-to-r from-transparent via-white/20 to-transparent"
                ></div>

                <span
                  v-if="!isGenerating"
                  class="relative flex items-center justify-center gap-2"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 sm:h-6 sm:w-6"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    stroke-width="2.5"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M13 10V3L4 14h7v7l9-11h-7z"
                    />
                  </svg>
                  <span class="tracking-wide font-semibold"
                    >Generate Your Trip with AI</span
                  >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 sm:h-6 sm:w-6 transform group-hover:translate-x-1 transition-transform duration-300"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    stroke-width="2.5"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M13 7l5 5m0 0l-5 5m5-5H6"
                    />
                  </svg>
                </span>
                <span
                  v-else
                  class="relative flex items-center justify-center gap-2"
                >
                  <svg
                    class="animate-spin h-5 w-5"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <circle
                      class="opacity-25"
                      cx="12"
                      cy="12"
                      r="10"
                      stroke="currentColor"
                      stroke-width="4"
                    ></circle>
                    <path
                      class="opacity-75"
                      fill="currentColor"
                      d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
                    ></path>
                  </svg>
                  <span class="font-semibold"
                    >Generating your amazing trip...</span
                  >
                </span>
              </button>
            </form>
          </div>
        </div>

        <!-- Generated Trip Plan -->
        <div
          v-if="generatedPlan"
          class="relative mt-6 sm:mt-8 backdrop-blur-xl bg-gradient-to-br from-white/[0.12] via-white/[0.08] to-white/[0.05] rounded-3xl shadow-[0_8px_32px_rgba(0,0,0,0.3)] p-5 sm:p-7 border border-white/30 ring-1 ring-white/20 overflow-hidden"
        >
          <!-- Decorative elements -->
          <div
            class="absolute top-0 right-0 w-32 h-32 bg-gradient-to-br from-purple-500/10 to-pink-500/10 rounded-full blur-3xl"
          ></div>

          <h2
            class="relative text-2xl sm:text-3xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 via-purple-300 to-pink-300 mb-5 flex items-center"
          >
            <span class="mr-2 sm:mr-3 text-2xl sm:text-3xl">🎉</span>
            <span class="leading-tight">Your Personalized Trip Plan</span>
          </h2>

          <!-- Itinerary -->
          <div class="relative mb-5 sm:mb-6">
            <h3
              class="text-lg sm:text-xl font-bold text-cyan-300 mb-3 flex items-center"
            >
              <span class="text-xl mr-2">📅</span>
              <span>Daily Itinerary</span>
            </h3>
            <div class="space-y-2.5">
              <div
                v-for="(day, index) in generatedPlan.itinerary"
                :key="index"
                class="bg-white/5 backdrop-blur-sm rounded-xl p-3 sm:p-4 border border-white/10 hover:border-cyan-400/30 transition-all duration-300 hover:bg-white/10"
              >
                <h4
                  class="text-sm sm:text-base font-semibold text-cyan-200 mb-1"
                >
                  Day {{ index + 1 }}
                </h4>
                <p class="text-blue-100/90 text-xs sm:text-sm leading-relaxed">
                  {{ day }}
                </p>
              </div>
            </div>
          </div>

          <!-- Hotels -->
          <div class="relative mb-5 sm:mb-6">
            <h3
              class="text-lg sm:text-xl font-bold text-purple-300 mb-3 flex items-center"
            >
              <span class="text-xl mr-2">🏨</span>
              <span>Recommended Hotels</span>
            </h3>
            <div class="space-y-2.5">
              <div
                v-for="(hotel, index) in generatedPlan.hotels"
                :key="index"
                class="bg-white/5 backdrop-blur-sm rounded-xl p-3 sm:p-4 border border-white/10 hover:border-purple-400/30 transition-all duration-300 hover:bg-white/10"
              >
                <div
                  class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-1 sm:gap-2"
                >
                  <div class="flex-1">
                    <h4 class="text-sm sm:text-base font-semibold text-white">
                      {{ hotel.name }}
                    </h4>
                    <p class="text-blue-100/80 text-xs">
                      📍 {{ hotel.location }}
                    </p>
                  </div>
                  <span
                    class="text-yellow-300 font-bold text-sm whitespace-nowrap bg-yellow-500/10 px-3 py-1 rounded-lg"
                    >${{ hotel.pricePerNight }}/night</span
                  >
                </div>
              </div>
            </div>
          </div>

          <!-- Transportation -->
          <div class="relative mb-5 sm:mb-6">
            <h3
              class="text-lg sm:text-xl font-bold text-green-300 mb-3 flex items-center"
            >
              <span class="text-xl mr-2">🚗</span>
              <span>Transportation</span>
            </h3>
            <div
              class="bg-white/5 backdrop-blur-sm rounded-xl p-3 sm:p-4 border border-white/10 hover:border-green-400/30 transition-all duration-300"
            >
              <p class="text-blue-100/90 text-xs sm:text-sm leading-relaxed">
                {{ generatedPlan.transportation }}
              </p>
            </div>
          </div>

          <!-- Total Cost -->
          <div
            class="relative bg-gradient-to-r from-yellow-500/20 via-orange-500/15 to-yellow-500/20 rounded-2xl p-4 border-2 border-yellow-400/50 shadow-lg hover:shadow-xl transition-all duration-300"
          >
            <div
              class="flex flex-col sm:flex-row justify-between items-center gap-2"
            >
              <h3
                class="text-lg sm:text-xl font-bold text-white text-center sm:text-left flex items-center"
              >
                <span class="text-xl sm:text-2xl mr-2">💵</span>
                <span>Estimated Total Cost</span>
              </h3>
              <span
                class="text-2xl sm:text-3xl font-bold text-yellow-300 bg-yellow-500/10 px-4 py-1 rounded-xl"
                >${{ generatedPlan.totalCost }}</span
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Trip form data
const tripData = ref({
  destination: "",
  startDate: "",
  endDate: "",
  budget: "",
  travelers: 1,
  preferences: "",
});

const isGenerating = ref(false);
const generatedPlan = ref(null);

// Generate trip plan using AI
const generateTripPlan = async () => {
  isGenerating.value = true;

  try {
    // Simulate API call (Replace this with actual Gemini AI API call)
    await new Promise((resolve) => setTimeout(resolve, 2000));

    // Calculate days
    const start = new Date(tripData.value.startDate);
    const end = new Date(tripData.value.endDate);
    const days = Math.ceil((end - start) / (1000 * 60 * 60 * 24)) + 1;

    // Generate mock plan (In production, this would come from Gemini AI API)
    generatedPlan.value = {
      itinerary: generateItinerary(days, tripData.value.destination),
      hotels: generateHotels(tripData.value.destination),
      transportation: generateTransportation(tripData.value.destination),
      totalCost: calculateTotalCost(days, tripData.value.budget),
    };

    // Scroll to results
    setTimeout(() => {
      window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
    }, 100);
  } catch (error) {
    console.error("Error generating trip plan:", error);
    alert("Failed to generate trip plan. Please try again.");
  } finally {
    isGenerating.value = false;
  }
};

// Helper functions (In production, these would be replaced by AI API responses)
const generateItinerary = (days, destination) => {
  const itinerary = [];
  for (let i = 0; i < days; i++) {
    itinerary.push(
      `Explore ${destination} - Visit popular landmarks, local markets, and enjoy authentic cuisine. Experience the culture and history of the area.`
    );
  }
  return itinerary;
};

const generateHotels = (destination) => {
  return [
    {
      name: "Grand Hotel " + destination,
      location: "City Center",
      pricePerNight: 120,
    },
    {
      name: "Boutique Inn " + destination,
      location: "Historic District",
      pricePerNight: 95,
    },
    {
      name: "Luxury Resort " + destination,
      location: "Beach Area",
      pricePerNight: 180,
    },
  ];
};

const generateTransportation = (destination) => {
  return `Recommended: Use local metro/subway system for daily travel (approx $50/week per person). Airport transfers via taxi or ride-sharing services ($30-50 each way). Consider renting a bike for exploring nearby areas.`;
};

const calculateTotalCost = (days, budget) => {
  // Simple estimation based on days and budget
  const hotelCost = days * 120;
  const foodCost = days * 60;
  const activityCost = days * 50;
  const transportCost = 150;
  return hotelCost + foodCost + activityCost + transportCost;
};
</script>

<style scoped>
/* Hide/beautify scrollbars slightly to avoid layout jitter */
.scrollbar-thin::-webkit-scrollbar {
  width: 8px;
}
.scrollbar-thin::-webkit-scrollbar-track {
  background: transparent;
}
.scrollbar-thin::-webkit-scrollbar-thumb {
  background-color: rgba(255, 255, 255, 0.18);
  border-radius: 8px;
  transition: background-color 0.3s ease;
}
.scrollbar-thin::-webkit-scrollbar-thumb:hover {
  background-color: rgba(255, 255, 255, 0.3);
}

/* Animated gradient for title */
@keyframes gradient-shift {
  0%,
  100% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
}

.animate-gradient {
  background-size: 200% auto;
  animation: gradient-shift 3s ease infinite;
}

/* Input field focus animations */
input:focus,
textarea:focus {
  transform: translateY(-1px);
}

/* Floating animation for decorative orbs */
@keyframes float {
  0%,
  100% {
    transform: translateY(0px) scale(1);
  }
  50% {
    transform: translateY(-20px) scale(1.05);
  }
}

/* Pulse animation for icons */
@keyframes pulse-soft {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.8;
  }
}
</style>
