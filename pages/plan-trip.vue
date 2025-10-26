<template>
  <div
    class="h-screen overflow-hidden bg-gradient-to-br from-[#0a0820] via-[#1a1040] to-[#0f0a30]"
  >
    <!-- Navigation Bar (same as home) -->
    <nav
      class="sticky top-0 z-50 bg-gradient-to-r from-[#0a0820]/95 via-[#1a1040]/95 to-[#0f0a30]/95 border-b border-purple-700/20 shadow-2xl backdrop-blur-md"
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
      class="relative h-[calc(100vh-4rem)] sm:h-[calc(100vh-5rem)] lg:h-[calc(100vh-6rem)]"
    >
      <!-- Decorative rail to visually separate scrollbar (keeps it subtle/inset) -->
      <div
        class="pointer-events-none absolute right-0 top-0 h-full w-3 sm:w-4 lg:w-5 bg-gradient-to-l from-[#0f0a30] via-[#0f0a30]/80 to-transparent rounded-l-xl"
      ></div>
      <div
        class="max-w-4xl mx-auto pr-6 sm:pr-10 lg:pr-14 pl-4 sm:pl-6 lg:pl-8 py-4 sm:py-6 h-full overflow-y-auto scrollbar-thin"
        style="scrollbar-gutter: stable both-edges"
      >
        <!-- Header -->
        <div
          class="sticky top-0 z-10 pb-3 sm:pb-4 bg-gradient-to-b from-[#0a0820]/80 via-[#1a1040]/70 to-transparent backdrop-blur-sm text-center mb-4 sm:mb-6 -mx-4 sm:mx-0 px-4"
        >
          <h1
            class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-2 sm:mb-3 drop-shadow-lg leading-tight"
          >
            Plan Your Dream Trip
          </h1>
          <p class="text-sm sm:text-base text-blue-100/90 px-4">
            Tell us where you want to go, and AI will create a personalized trip
            plan for you
          </p>
        </div>

        <!-- Trip Form -->
        <div
          class="backdrop-blur-md bg-white/10 rounded-2xl shadow-2xl p-4 sm:p-6 md:p-8 border border-white/20 ring-1 ring-white/10"
        >
          <form
            @submit.prevent="generateTripPlan"
            class="space-y-5 sm:space-y-6"
          >
            <!-- Destination Input -->
            <div>
              <label
                class="block text-white font-semibold mb-2 text-base sm:text-lg"
              >
                📍 Where do you want to go?
              </label>
              <input
                v-model="tripData.destination"
                type="text"
                placeholder="Enter destination (e.g., Paris, France)"
                required
                class="w-full px-3 sm:px-4 py-3 sm:py-4 bg-white/90 border-2 border-blue-300 rounded-xl focus:outline-none focus:ring-4 focus:ring-blue-500 focus:border-transparent text-gray-900 text-base sm:text-lg placeholder-gray-500 transition-all"
              />
            </div>

            <!-- Date Range -->
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-4">
              <div>
                <label
                  class="block text-white font-semibold mb-2 text-sm sm:text-base"
                >
                  📅 Start Date
                </label>
                <input
                  v-model="tripData.startDate"
                  type="date"
                  required
                  class="w-full px-3 sm:px-4 py-2.5 sm:py-3 bg-white/90 border-2 border-blue-300 rounded-xl focus:outline-none focus:ring-4 focus:ring-blue-500 text-gray-900 text-sm sm:text-base transition-all"
                />
              </div>
              <div>
                <label
                  class="block text-white font-semibold mb-2 text-sm sm:text-base"
                >
                  📅 End Date
                </label>
                <input
                  v-model="tripData.endDate"
                  type="date"
                  required
                  class="w-full px-3 sm:px-4 py-2.5 sm:py-3 bg-white/90 border-2 border-blue-300 rounded-xl focus:outline-none focus:ring-4 focus:ring-blue-500 text-gray-900 text-sm sm:text-base transition-all"
                />
              </div>
            </div>

            <!-- Budget -->
            <div>
              <label
                class="block text-white font-semibold mb-2 text-base sm:text-lg"
              >
                💰 Budget (USD)
              </label>
              <input
                v-model="tripData.budget"
                type="number"
                placeholder="Enter your budget"
                required
                class="w-full px-3 sm:px-4 py-3 sm:py-4 bg-white/90 border-2 border-blue-300 rounded-xl focus:outline-none focus:ring-4 focus:ring-blue-500 text-gray-900 text-base sm:text-lg placeholder-gray-500 transition-all"
              />
            </div>

            <!-- Travelers -->
            <div>
              <label
                class="block text-white font-semibold mb-2 text-base sm:text-lg"
              >
                👥 Number of Travelers
              </label>
              <input
                v-model="tripData.travelers"
                type="number"
                min="1"
                placeholder="How many people?"
                required
                class="w-full px-3 sm:px-4 py-3 sm:py-4 bg-white/90 border-2 border-blue-300 rounded-xl focus:outline-none focus:ring-4 focus:ring-blue-500 text-gray-900 text-base sm:text-lg placeholder-gray-500 transition-all"
              />
            </div>

            <!-- Preferences -->
            <div>
              <label
                class="block text-white font-semibold mb-2 text-base sm:text-lg"
              >
                ⭐ Travel Preferences
              </label>
              <textarea
                v-model="tripData.preferences"
                rows="3"
                placeholder="Tell us about your interests... (e.g., adventure, culture, food, relaxation)"
                class="w-full px-3 sm:px-4 py-3 sm:py-4 bg-white/90 border-2 border-blue-300 rounded-xl focus:outline-none focus:ring-4 focus:ring-blue-500 text-gray-900 text-base sm:text-lg placeholder-gray-500 resize-none transition-all"
              ></textarea>
            </div>

            <!-- Submit Button -->
            <button
              type="submit"
              :disabled="isGenerating"
              class="group relative w-full py-5 sm:py-6 bg-gradient-to-r from-[#FF6B6B] via-[#FF4E9A] to-[#B620E0] hover:from-[#FF5252] hover:via-[#FF3D8F] hover:to-[#A00FD0] text-white font-bold rounded-full shadow-[0_10px_40px_rgba(255,78,154,0.4)] hover:shadow-[0_15px_50px_rgba(255,78,154,0.6)] transition-all duration-500 transform hover:scale-[1.02] text-lg sm:text-xl md:text-2xl disabled:opacity-50 disabled:cursor-not-allowed overflow-hidden"
            >
              <div
                class="absolute inset-0 bg-gradient-to-r from-[#FF8E8E] via-[#FF6BB5] to-[#D040FF] opacity-0 group-hover:opacity-30 transition-opacity duration-500"
              ></div>
              <span
                v-if="!isGenerating"
                class="relative flex items-center justify-center gap-2 sm:gap-3"
              >
                <span class="tracking-wide">Generate Your Trip with AI</span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6 sm:h-7 sm:w-7 transform group-hover:translate-x-2 transition-transform duration-300"
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
                class="relative flex items-center justify-center gap-3"
              >
                <svg
                  class="animate-spin h-6 w-6"
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
                <span>Generating your amazing trip...</span>
              </span>
            </button>
          </form>
        </div>

        <!-- Generated Trip Plan -->
        <div
          v-if="generatedPlan"
          class="mt-8 sm:mt-12 backdrop-blur-md bg-white/10 rounded-2xl sm:rounded-3xl shadow-2xl p-5 sm:p-8 md:p-10 border border-white/20"
        >
          <h2
            class="text-2xl sm:text-3xl font-bold text-white mb-5 sm:mb-6 flex items-center"
          >
            <span class="mr-2 sm:mr-3 text-2xl sm:text-3xl">🎉</span>
            <span class="leading-tight">Your Personalized Trip Plan</span>
          </h2>

          <!-- Itinerary -->
          <div class="mb-6 sm:mb-8">
            <h3
              class="text-xl sm:text-2xl font-bold text-cyan-300 mb-3 sm:mb-4"
            >
              📅 Daily Itinerary
            </h3>
            <div class="space-y-3 sm:space-y-4">
              <div
                v-for="(day, index) in generatedPlan.itinerary"
                :key="index"
                class="bg-white/10 rounded-xl p-3 sm:p-4 border border-white/10"
              >
                <h4
                  class="text-base sm:text-xl font-semibold text-white mb-1 sm:mb-2"
                >
                  Day {{ index + 1 }}
                </h4>
                <p class="text-blue-100 text-sm sm:text-base">{{ day }}</p>
              </div>
            </div>
          </div>

          <!-- Hotels -->
          <div class="mb-6 sm:mb-8">
            <h3
              class="text-xl sm:text-2xl font-bold text-purple-300 mb-3 sm:mb-4"
            >
              🏨 Recommended Hotels
            </h3>
            <div class="space-y-3">
              <div
                v-for="(hotel, index) in generatedPlan.hotels"
                :key="index"
                class="bg-white/10 rounded-xl p-3 sm:p-4 border border-white/10"
              >
                <div
                  class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2"
                >
                  <div class="flex-1">
                    <h4 class="text-base sm:text-lg font-semibold text-white">
                      {{ hotel.name }}
                    </h4>
                    <p class="text-blue-100 text-xs sm:text-sm">
                      {{ hotel.location }}
                    </p>
                  </div>
                  <span
                    class="text-yellow-300 font-bold text-sm sm:text-base whitespace-nowrap"
                    >${{ hotel.pricePerNight }}/night</span
                  >
                </div>
              </div>
            </div>
          </div>

          <!-- Transportation -->
          <div class="mb-6 sm:mb-8">
            <h3
              class="text-xl sm:text-2xl font-bold text-green-300 mb-3 sm:mb-4"
            >
              🚗 Transportation
            </h3>
            <div
              class="bg-white/10 rounded-xl p-3 sm:p-4 border border-white/10"
            >
              <p class="text-blue-100 text-sm sm:text-base">
                {{ generatedPlan.transportation }}
              </p>
            </div>
          </div>

          <!-- Total Cost -->
          <div
            class="bg-gradient-to-r from-yellow-500/20 to-orange-500/20 rounded-xl p-4 sm:p-6 border-2 border-yellow-400"
          >
            <div
              class="flex flex-col sm:flex-row justify-between items-center gap-3 sm:gap-0"
            >
              <h3
                class="text-xl sm:text-2xl font-bold text-white text-center sm:text-left"
              >
                💵 Estimated Total Cost
              </h3>
              <span class="text-2xl sm:text-3xl font-bold text-yellow-300"
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
}
</style>
