<template>
  <div
    id="choose-our-service"
    class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-10 sm:mb-12">
        <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3">
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
        <!-- Service Cards Array -->
        <div
          v-for="(service, index) in services"
          :key="index"
          class="group backdrop-blur-xl bg-white/5 rounded-2xl p-5 sm:p-6 border border-white/10 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 cursor-pointer flex flex-col items-center"
          :class="service.hoverClass"
        >
          <div
            class="w-16 h-16 sm:w-18 sm:h-18 mb-4 flex items-center justify-center group-hover:scale-110 transition-transform duration-300"
          >
            <span class="text-4xl">{{ service.icon }}</span>
          </div>
          <h3 class="text-sm sm:text-base font-semibold text-white text-center">
            {{ service.title }}
          </h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const services = ref([
  {
    title: "Currency Exchange",
    icon: "💱",
    hoverClass: "hover:border-yellow-400/50 hover:shadow-yellow-500/20",
  },
  {
    title: "Bus Reservation",
    icon: "🚌",
    hoverClass: "hover:border-red-400/50 hover:shadow-red-500/20",
  },
  {
    title: "Bus Ticket",
    icon: "🎫",
    hoverClass: "hover:border-purple-400/50 hover:shadow-purple-500/20",
  },
  {
    title: "Train Booking",
    icon: "🚆",
    hoverClass: "hover:border-orange-400/50 hover:shadow-orange-500/20",
  },
  {
    title: "Cruise Ship",
    icon: "🚢",
    hoverClass: "hover:border-blue-400/50 hover:shadow-blue-500/20",
  },
  {
    title: "Travel Insurance",
    icon: "🛡️",
    hoverClass: "hover:border-teal-400/50 hover:shadow-teal-500/20",
  },
  {
    title: "Visa Services",
    icon: "📘",
    hoverClass: "hover:border-indigo-400/50 hover:shadow-indigo-500/20",
  },
  {
    title: "Work Visa",
    icon: "💼",
    hoverClass: "hover:border-cyan-400/50 hover:shadow-cyan-500/20",
  },
  {
    title: "Medical Tourism",
    icon: "⚕️",
    hoverClass: "hover:border-pink-400/50 hover:shadow-pink-500/20",
  },
  {
    title: "Car Rental",
    icon: "🚗",
    hoverClass: "hover:border-green-400/50 hover:shadow-green-500/20",
  },
  {
    title: "Flight Tickets",
    icon: "✈️",
    hoverClass: "hover:border-yellow-400/50 hover:shadow-yellow-500/20",
  },
  {
    title: "Visa Consulting",
    icon: "👔",
    hoverClass: "hover:border-red-400/50 hover:shadow-red-500/20",
  },
]);
</script>
