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
            class="w-16 h-16 sm:w-18 sm:h-18 mb-4 rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300 text-white"
            :class="service.gradientClass"
            v-html="service.svg"
          ></div>
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
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>',
    gradientClass: "bg-gradient-to-br from-yellow-400 to-orange-500",
    hoverClass: "hover:border-yellow-400/50 hover:shadow-yellow-500/20",
  },
  {
    title: "Bus Reservation",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7v8a2 2 0 002 2h6M8 7V5a2 2 0 012-2h4.586a1 1 0 01.707.293l4.414 4.414a1 1 0 01.293.707V15a2 2 0 01-2 2h-2M8 7H6a2 2 0 00-2 2v10a2 2 0 002 2h8a2 2 0 002-2v-2"/></svg>',
    gradientClass: "bg-gradient-to-br from-red-400 to-pink-500",
    hoverClass: "hover:border-red-400/50 hover:shadow-red-500/20",
  },
  {
    title: "Bus Ticket",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 5v2m0 4v2m0 4v2M5 5a2 2 0 00-2 2v3a2 2 0 110 4v3a2 2 0 002 2h14a2 2 0 002-2v-3a2 2 0 110-4V7a2 2 0 00-2-2H5z"/></svg>',
    gradientClass: "bg-gradient-to-br from-purple-400 to-pink-500",
    hoverClass: "hover:border-purple-400/50 hover:shadow-purple-500/20",
  },
  {
    title: "Train Booking",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>',
    gradientClass: "bg-gradient-to-br from-orange-400 to-red-500",
    hoverClass: "hover:border-orange-400/50 hover:shadow-orange-500/20",
  },
  {
    title: "Cruise Ship",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4.001 4.001 0 003 15z"/></svg>',
    gradientClass: "bg-gradient-to-br from-blue-400 to-cyan-500",
    hoverClass: "hover:border-blue-400/50 hover:shadow-blue-500/20",
  },
  {
    title: "Travel Insurance",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/></svg>',
    gradientClass: "bg-gradient-to-br from-teal-400 to-green-500",
    hoverClass: "hover:border-teal-400/50 hover:shadow-teal-500/20",
  },
  {
    title: "Visa Services",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/></svg>',
    gradientClass: "bg-gradient-to-br from-indigo-400 to-purple-500",
    hoverClass: "hover:border-indigo-400/50 hover:shadow-indigo-500/20",
  },
  {
    title: "Work Visa",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>',
    gradientClass: "bg-gradient-to-br from-cyan-400 to-blue-500",
    hoverClass: "hover:border-cyan-400/50 hover:shadow-cyan-500/20",
  },
  {
    title: "Medical Tourism",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"/></svg>',
    gradientClass: "bg-gradient-to-br from-pink-400 to-rose-500",
    hoverClass: "hover:border-pink-400/50 hover:shadow-pink-500/20",
  },
  {
    title: "Car Rental",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7h12m0 0l-4-4m4 4l-4 4m0 6H4m0 0l4 4m-4-4l4-4"/></svg>',
    gradientClass: "bg-gradient-to-br from-green-400 to-emerald-500",
    hoverClass: "hover:border-green-400/50 hover:shadow-green-500/20",
  },
  {
    title: "Flight Tickets",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"/></svg>',
    gradientClass: "bg-gradient-to-br from-yellow-400 to-amber-500",
    hoverClass: "hover:border-yellow-400/50 hover:shadow-yellow-500/20",
  },
  {
    title: "Visa Consulting",
    svg: '<svg class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/></svg>',
    gradientClass: "bg-gradient-to-br from-red-400 to-orange-500",
    hoverClass: "hover:border-red-400/50 hover:shadow-red-500/20",
  },
]);
</script>
