<template>
  <div
    class="h-screen bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542] flex items-center justify-center px-4 sm:px-6 lg:px-8 overflow-hidden"
  >
    <!-- Animated Starry Background -->
    <div class="absolute inset-0 stars-container">
      <div class="stars-layer stars-layer-1"></div>
      <div class="stars-layer stars-layer-2"></div>
      <div class="stars-layer stars-layer-3"></div>
    </div>

    <div class="relative z-10 w-full max-w-md">
      <!-- Logo/Back -->
      <NuxtLink
        to="/"
        class="flex items-center space-x-2 mb-3 text-white hover:text-cyan-300 transition-colors group"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5 sm:h-6 sm:w-6 transform group-hover:-translate-x-1 transition-transform"
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
        <span class="font-semibold text-sm sm:text-base">Back to Home</span>
      </NuxtLink>

      <!-- Sign Up Form -->
      <div
        class="backdrop-blur-md bg-[#2a2d4a]/80 rounded-2xl shadow-2xl p-4 sm:p-6 border border-white/10"
      >
        <div class="text-center mb-3 sm:mb-4">
          <h1 class="text-xl sm:text-2xl md:text-3xl font-bold text-white mb-1">
            Create Account
          </h1>
          <p class="text-gray-300 text-xs sm:text-sm">
            Start your travel journey today
          </p>
        </div>

        <form @submit.prevent="handleSignUp" class="space-y-2.5 sm:space-y-3">
          <!-- Name -->
          <div>
            <label
              class="block text-white font-medium mb-2 text-sm sm:text-base"
              >Full Name</label
            >
            <input
              v-model="formData.name"
              type="text"
              required
              placeholder="Enter your full name"
              class="w-full px-4 py-3 sm:py-3.5 bg-white/95 border-2 border-transparent focus:border-cyan-500 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500/30 text-gray-900 placeholder-gray-500 text-sm sm:text-base transition-all"
            />
          </div>

          <!-- Email -->
          <div>
            <label
              class="block text-white font-medium mb-2 text-sm sm:text-base"
              >Email</label
            >
            <input
              v-model="formData.email"
              type="email"
              required
              placeholder="Enter your email"
              class="w-full px-4 py-3 sm:py-3.5 bg-white/95 border-2 border-transparent focus:border-cyan-500 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500/30 text-gray-900 placeholder-gray-500 text-sm sm:text-base transition-all"
            />
          </div>

          <!-- Password -->
          <div>
            <label
              class="block text-white font-medium mb-2 text-sm sm:text-base"
              >Password</label
            >
            <input
              v-model="formData.password"
              type="password"
              required
              placeholder="Create a password"
              class="w-full px-4 py-3 sm:py-3.5 bg-white/95 border-2 border-transparent focus:border-cyan-500 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500/30 text-gray-900 placeholder-gray-500 text-sm sm:text-base transition-all"
            />
          </div>

          <!-- Confirm Password -->
          <div>
            <label
              class="block text-white font-medium mb-2 text-sm sm:text-base"
              >Confirm Password</label
            >
            <input
              v-model="formData.confirmPassword"
              type="password"
              required
              placeholder="Confirm your password"
              class="w-full px-4 py-3 sm:py-3.5 bg-white/95 border-2 border-transparent focus:border-cyan-500 rounded-xl focus:outline-none focus:ring-2 focus:ring-cyan-500/30 text-gray-900 placeholder-gray-500 text-sm sm:text-base transition-all"
            />
          </div>

          <!-- Terms -->
          <label
            class="flex items-start space-x-2 text-gray-300 cursor-pointer"
          >
            <input
              type="checkbox"
              required
              class="w-4 h-4 rounded mt-1 accent-cyan-500"
            />
            <span class="text-xs sm:text-sm"
              >I agree to the Terms of Service and Privacy Policy</span
            >
          </label>

          <!-- Submit Button -->
          <button
            type="submit"
            class="w-full py-3 sm:py-3.5 md:py-4 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold rounded-xl shadow-2xl shadow-cyan-500/20 transition-all duration-300 transform hover:scale-[1.02] text-sm sm:text-base mt-2"
          >
            Create Account
          </button>
        </form>

        <!-- Divider -->
        <div class="relative my-3">
          <div class="absolute inset-0 flex items-center">
            <div class="w-full border-t border-white/20"></div>
          </div>
          <div class="relative flex justify-center text-xs">
            <span class="px-3 bg-[#2a2d4a] text-gray-400"
              >Or continue with</span
            >
          </div>
        </div>

        <!-- Social Login -->
        <div class="grid grid-cols-2 gap-2.5 sm:gap-3 mb-3">
          <button
            class="flex items-center justify-center space-x-1.5 py-2 bg-white/10 hover:bg-white/20 rounded-xl transition-all border border-white/20"
          >
            <span class="text-base sm:text-lg">🔍</span>
            <span class="text-white font-medium text-xs">Google</span>
          </button>
          <button
            class="flex items-center justify-center space-x-1.5 py-2 bg-white/10 hover:bg-white/20 rounded-xl transition-all border border-white/20"
          >
            <span class="text-base sm:text-lg">📘</span>
            <span class="text-white font-medium text-xs">Facebook</span>
          </button>
        </div>

        <!-- Sign In Link -->
        <p class="text-center text-gray-300 text-xs">
          Already have an account?
          <NuxtLink
            to="/sign-in"
            class="text-cyan-400 hover:text-cyan-300 font-semibold transition-colors"
            >Sign In</NuxtLink
          >
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const formData = ref({
  name: "",
  email: "",
  password: "",
  confirmPassword: "",
});

const handleSignUp = () => {
  if (formData.value.password !== formData.value.confirmPassword) {
    alert("Passwords do not match!");
    return;
  }

  // In a real app, you would call an authentication API here
  console.log("Sign up:", formData.value);
  alert("Account created successfully!");
  router.push("/sign-in");
};
</script>

<style scoped>
/* Stars animation */
.stars-container {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.stars-layer {
  position: absolute;
  width: 100%;
  height: 100%;
  background-repeat: repeat;
  background-position: center;
}

.stars-layer-1 {
  background-image: radial-gradient(1px 1px at 20px 30px, white, transparent),
    radial-gradient(1px 1px at 60px 70px, white, transparent),
    radial-gradient(1px 1px at 50px 160px, white, transparent),
    radial-gradient(1px 1px at 130px 80px, white, transparent),
    radial-gradient(1px 1px at 140px 150px, white, transparent);
  background-size: 400px 200px;
  animation: stars-float-1 80s linear infinite;
  opacity: 0.6;
}

.stars-layer-2 {
  background-image: radial-gradient(
      1.5px 1.5px at 80px 50px,
      rgba(255, 255, 255, 0.9),
      transparent
    ),
    radial-gradient(
      1.5px 1.5px at 180px 140px,
      rgba(255, 255, 255, 0.9),
      transparent
    );
  background-size: 450px 250px;
  animation: stars-float-2 100s linear infinite;
  opacity: 0.5;
}

.stars-layer-3 {
  background-image: radial-gradient(
      2px 2px at 40px 80px,
      rgba(255, 255, 255, 1),
      transparent
    ),
    radial-gradient(2px 2px at 150px 30px, rgba(255, 255, 255, 1), transparent);
  background-size: 500px 280px;
  animation: stars-float-3 120s linear infinite;
  opacity: 0.7;
}

@keyframes stars-float-1 {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-200px);
  }
}

@keyframes stars-float-2 {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-250px);
  }
}

@keyframes stars-float-3 {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-280px);
  }
}
</style>
