<template>
  <footer
    class="bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542] text-white"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 sm:py-16">
      <!-- Main Footer Content -->
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 sm:gap-10 mb-10"
      >
        <!-- Company Info -->
        <div class="col-span-1 sm:col-span-2 lg:col-span-1">
          <div class="flex items-center gap-2 mb-4">
            <div class="w-10 h-10 rounded-lg flex items-center justify-center">
              <img
                src="/images/Ai-powerd-owl.png"
                alt="AI Trip Planner Logo"
                class="w-10 h-10 object-contain"
              />
            </div>
            <h3
              class="text-xl font-bold bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent"
            >
              AI Trip Planner
            </h3>
          </div>
          <p class="text-gray-400 text-sm mb-4 leading-relaxed">
            Your intelligent travel companion. Plan, explore, and experience the
            world with AI-powered itineraries.
          </p>
        </div>

        <!-- Quick Links Sections -->
        <div
          v-for="(section, index) in footerLinks"
          :key="index"
          class="col-span-1"
        >
          <h4 class="text-lg font-bold text-white mb-4">{{ section.title }}</h4>
          <ul class="space-y-2">
            <li v-for="(link, idx) in section.links" :key="idx">
              <a
                href="#"
                class="text-gray-400 hover:text-cyan-400 text-sm transition-colors"
              >
                {{ link }}
              </a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Footer Bottom -->
      <div
        class="border-t border-white/10 pt-8 flex flex-col md:flex-row justify-between items-center gap-4"
      >
        <p class="text-gray-400 text-sm text-center md:text-left">
          © 2024 AI Trip Planner. All rights reserved.
        </p>
        <div class="flex gap-6 text-sm">
          <a
            href="#"
            class="text-gray-400 hover:text-cyan-400 transition-colors"
          >
            Privacy Policy
          </a>
          <a
            href="#"
            class="text-gray-400 hover:text-cyan-400 transition-colors"
          >
            Terms of Service
          </a>
          <a
            href="#"
            class="text-gray-400 hover:text-cyan-400 transition-colors"
          >
            Cookie Policy
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from "vue";

const footerLinks = ref([
  {
    title: "Company",
    links: ["About Us", "Careers", "Press", "Blog", "Contact"],
  },
  {
    title: "Support",
    links: ["Help Center", "Safety", "FAQs", "Privacy", "Terms"],
  },
  {
    title: "Explore",
    links: ["Destinations", "Travel Tips", "Guides", "Reviews", "Community"],
  },
]);
</script>
