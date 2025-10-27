<template>
  <div
    id="guest-reviews"
    class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-10 sm:mb-12">
        <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3">
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
        <!-- Review Cards -->
        <div
          v-for="(review, index) in reviews"
          :key="index"
          class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 sm:p-8 border border-white/10 transition-all duration-300 transform hover:-translate-y-2"
          :class="review.hoverClass"
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
            {{ review.text }}
          </p>

          <!-- Reviewer Info -->
          <div class="flex items-center gap-4">
            <div
              class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold text-lg"
              :class="review.gradientClass"
            >
              {{ review.initials }}
            </div>
            <div>
              <h4 class="text-white font-semibold">{{ review.name }}</h4>
              <p class="text-gray-400 text-xs">{{ review.location }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const reviews = ref([
  {
    text: "AI Trip Planner made my European vacation absolutely seamless! The itinerary was perfectly tailored to my interests and budget. Highly recommended!",
    name: "Sarah Mitchell",
    location: "Traveled to Paris, France",
    initials: "SM",
    gradientClass: "bg-gradient-to-br from-cyan-400 to-blue-600",
    hoverClass: "hover:border-cyan-400/50",
  },
  {
    text: "The AI suggestions were spot-on! Found hidden gems I wouldn't have discovered otherwise. The trip planning process was effortless and fun.",
    name: "James Chen",
    location: "Traveled to Tokyo, Japan",
    initials: "JC",
    gradientClass: "bg-gradient-to-br from-purple-400 to-pink-600",
    hoverClass: "hover:border-purple-400/50",
  },
  {
    text: "Best travel planning tool I've used! Saved me hours of research. The personalized recommendations were exactly what I was looking for.",
    name: "Emily Rodriguez",
    location: "Traveled to Bali, Indonesia",
    initials: "ER",
    gradientClass: "bg-gradient-to-br from-green-400 to-emerald-600",
    hoverClass: "hover:border-green-400/50",
  },
]);
</script>
