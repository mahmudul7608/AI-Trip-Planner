<template>
  <div
    id="contact"
    class="py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Section Header -->
      <div class="text-center mb-10 sm:mb-12">
        <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-3">
          Contact
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-purple-400 to-pink-400"
          >
            Us
          </span>
        </h2>
        <p class="text-sm sm:text-base text-gray-400 max-w-2xl mx-auto">
          Have questions or need assistance? We're here to help you plan your
          perfect trip
        </p>
      </div>

      <!-- Contact Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-10">
        <!-- Contact Form -->
        <div
          class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 sm:p-8 border border-white/10 shadow-2xl"
        >
          <h3 class="text-2xl font-bold text-white mb-6">Send us a Message</h3>
          <form @submit.prevent="handleSubmit" class="space-y-5">
            <!-- Name -->
            <div>
              <label class="block text-white font-semibold mb-2 text-sm">
                Your Name
              </label>
              <input
                v-model="form.name"
                type="text"
                required
                placeholder="John Doe"
                class="w-full px-4 py-3 bg-white/10 border border-white/20 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent text-white placeholder-gray-400 transition-all"
              />
            </div>

            <!-- Email -->
            <div>
              <label class="block text-white font-semibold mb-2 text-sm">
                Email Address
              </label>
              <input
                v-model="form.email"
                type="email"
                required
                placeholder="john@example.com"
                class="w-full px-4 py-3 bg-white/10 border border-white/20 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent text-white placeholder-gray-400 transition-all"
              />
            </div>

            <!-- Message -->
            <div>
              <label class="block text-white font-semibold mb-2 text-sm">
                Message
              </label>
              <textarea
                v-model="form.message"
                required
                rows="4"
                placeholder="Tell us how we can help you..."
                class="w-full px-4 py-3 bg-white/10 border border-white/20 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent text-white placeholder-gray-400 transition-all resize-none"
              ></textarea>
            </div>

            <!-- Submit Button -->
            <button
              type="submit"
              class="w-full py-4 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold rounded-xl shadow-lg shadow-cyan-500/30 hover:shadow-xl hover:shadow-cyan-500/50 transition-all duration-300 transform hover:scale-105"
            >
              Send Message
            </button>
          </form>
        </div>

        <!-- Contact Information -->
        <div class="space-y-5">
          <!-- Contact Cards -->
          <div
            v-for="(contact, index) in contactInfo"
            :key="index"
            class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 border border-white/10 transition-all duration-300 group"
            :class="contact.hoverClass"
          >
            <div class="flex items-start gap-4">
              <div
                class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 group-hover:scale-110 transition-transform duration-300"
                :class="contact.gradientClass"
              >
                <span class="text-2xl">{{ contact.icon }}</span>
              </div>
              <div>
                <h4 class="text-lg font-bold text-white mb-2">
                  {{ contact.title }}
                </h4>
                <p
                  class="text-gray-300 text-sm mb-1"
                  v-for="(line, idx) in contact.lines"
                  :key="idx"
                >
                  {{ line }}
                </p>
              </div>
            </div>
          </div>

          <!-- Social Media -->
          <div
            class="backdrop-blur-xl bg-white/5 rounded-2xl p-6 border border-white/10"
          >
            <h4 class="text-lg font-bold text-white mb-4">Connect With Us</h4>
            <div class="flex gap-3">
              <a
                v-for="(social, index) in socials"
                :key="index"
                href="#"
                class="w-10 h-10 bg-white/10 rounded-lg flex items-center justify-center transition-all duration-300 hover:scale-110"
                :class="social.hoverClass"
              >
                <span class="text-lg">{{ social.icon }}</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const form = ref({
  name: "",
  email: "",
  message: "",
});

const contactInfo = ref([
  {
    title: "Email Us",
    icon: "✉️",
    lines: ["support@aitripplanner.com", "info@aitripplanner.com"],
    gradientClass: "bg-gradient-to-br from-cyan-400 to-blue-600",
    hoverClass: "hover:border-cyan-400/50",
  },
  {
    title: "Call Us",
    icon: "📞",
    lines: ["+1 (555) 123-4567", "Mon-Fri 9am to 6pm EST"],
    gradientClass: "bg-gradient-to-br from-purple-400 to-pink-600",
    hoverClass: "hover:border-purple-400/50",
  },
  {
    title: "Visit Us",
    icon: "📍",
    lines: ["123 Travel Street", "San Francisco, CA 94102, USA"],
    gradientClass: "bg-gradient-to-br from-green-400 to-emerald-600",
    hoverClass: "hover:border-green-400/50",
  },
]);

const socials = ref([
  { icon: "📘", hoverClass: "hover:bg-cyan-500" },
  { icon: "🐦", hoverClass: "hover:bg-blue-400" },
  { icon: "📷", hoverClass: "hover:bg-pink-500" },
  { icon: "💼", hoverClass: "hover:bg-blue-600" },
]);

const handleSubmit = () => {
  console.log("Form submitted:", form.value);
  alert("Thank you! Your message has been sent.");
  form.value = { name: "", email: "", message: "" };
};
</script>
