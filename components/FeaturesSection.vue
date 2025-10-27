<template>
  <div
    id="why-choose-us"
    class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
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
          Experience the future of travel planning with our AI-powered platform
        </p>
      </div>

      <!-- Features Grid -->
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5 sm:gap-6 lg:gap-8"
      >
        <!-- Feature Cards -->
        <div
          v-for="(feature, index) in features"
          :key="index"
          class="group backdrop-blur-md bg-white/5 rounded-xl sm:rounded-2xl p-6 sm:p-8 border border-white/10 transition-all duration-300 transform hover:-translate-y-2"
          :class="feature.hoverClass"
        >
          <div
            class="w-12 h-12 sm:w-16 sm:h-16 rounded-lg sm:rounded-xl flex items-center justify-center mb-4 sm:mb-6 group-hover:scale-110 transition-transform"
            :class="feature.gradientClass"
          >
            <span class="text-2xl sm:text-3xl">{{ feature.icon }}</span>
          </div>
          <h3 class="text-xl sm:text-2xl font-bold text-white mb-2 sm:mb-3">
            {{ feature.title }}
          </h3>
          <p class="text-sm sm:text-base text-gray-300">
            {{ feature.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const features = ref([
  {
    title: "Smart Destinations",
    icon: "✈️",
    description:
      "AI-powered destination recommendations tailored to your preferences and budget",
    gradientClass: "bg-gradient-to-br from-cyan-400 to-blue-500",
    hoverClass: "hover:border-cyan-400/50",
  },
  {
    title: "Itinerary Planning",
    icon: "📅",
    description:
      "Personalized day-by-day schedules with optimal routes and timings",
    gradientClass: "bg-gradient-to-br from-purple-400 to-pink-500",
    hoverClass: "hover:border-purple-400/50",
  },
  {
    title: "Budget Optimization",
    icon: "💰",
    description:
      "Get the most value from your trip with smart cost-saving suggestions",
    gradientClass: "bg-gradient-to-br from-green-400 to-emerald-500",
    hoverClass: "hover:border-green-400/50",
  },
  {
    title: "Hotel Booking",
    icon: "🏨",
    description: "Find and book the perfect accommodation for your stay",
    gradientClass: "bg-gradient-to-br from-yellow-400 to-orange-500",
    hoverClass: "hover:border-yellow-400/50",
  },
  {
    title: "Interactive Maps",
    icon: "🗺️",
    description: "Explore destinations with detailed interactive world maps",
    gradientClass: "bg-gradient-to-br from-red-400 to-pink-500",
    hoverClass: "hover:border-red-400/50",
  },
  {
    title: "Travel Analytics",
    icon: "📊",
    description: "Track your travel history and get personalized insights",
    gradientClass: "bg-gradient-to-br from-indigo-400 to-purple-500",
    hoverClass: "hover:border-indigo-400/50",
  },
]);
</script>
