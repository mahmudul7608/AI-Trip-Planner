<template>
  <div
    class="min-h-screen bg-gradient-to-br from-[#1a1f3a] via-[#2d3561] to-[#1e2542]"
  >
    <Navbar />
    <HeroSection />
    <StatisticsSection />
    <AITripBuilder />
    <ServicesSection />
    <FeaturesSection />
    <ReviewsSection />
    <CTASection />
    <ContactSection />
    <Footer />
  </div>
</template>

<script setup>
import Navbar from "~/components/Navbar.vue";
import HeroSection from "~/components/HeroSection.vue";
import StatisticsSection from "~/components/StatisticsSection.vue";
import AITripBuilder from "~/components/AITripBuilder.vue";
import ServicesSection from "~/components/ServicesSection.vue";
import FeaturesSection from "~/components/FeaturesSection.vue";
import ReviewsSection from "~/components/ReviewsSection.vue";
import CTASection from "~/components/CTASection.vue";
import ContactSection from "~/components/ContactSection.vue";
import Footer from "~/components/Footer.vue";
</script>
