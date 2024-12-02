<template>
  <div class="relative min-h-screen bg-gray-900">
    <!-- Three.js Scene Component -->
    <!-- This component renders a Three.js scene as a fixed background layer covering the entire screen -->
    <ThreeSun class="absolute inset-0 w-full h-full" />

    <!-- Contact Content Overlay -->
    <!-- Overlay container for the main content, positioned relative to the background -->
    <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-0 pt-20">
      <!-- Padding to avoid overlap with fixed header -->
        
      <!-- Additional Content Sections Wrapper -->     
      <div class="bg-black bg-opacity-25 p-8 rounded-lg max-w-5xl w-full mx-4 border border-neutral-100">
        <header class="text-center mb-6 max-w-2xl mx-auto mt-8">
          <h1 class="text-4xl font-exo mb-4 italic text-neutral-100">CONTACT US</h1>
        </header>
        <section class="grid grid-cols-1 md:grid-cols-2 gap-8 rounded-lg bg-black bg-opacity-0 p-10">
          <!-- Left Column: Text Content -->
          <div class="flex flex-col p-6 rounded-xl bg-black bg-opacity-50 border border-neutral-100">
            <h1 class="text-4xl font-exo mb-4 italic text-neutral-100">Get in touch</h1>
            <p class="text-neutral-100">
              Reach out by phone, text, or email. We're standing by to help you with service inquiries, customer service, or just general questions.
            </p>
          </div>
          <!-- Right Column: Text Content -->
          <div class="flex flex-col p-6 rounded-xl bg-black bg-opacity-50 border border-neutral-100">
            <h3 class="text-2xl font-semibold mb-3 text-white">Call Us</h3>
            <p class="text-gray-200">
              7 a.m.–5 p.m. (PT), Monday–Friday<br>
              <a href="tel:+19252898382" class="text-blue-400 hover:underline">+1-925-289-8382</a><br><br>
            </p>
            <h3 class="text-2xl font-semibold mb-3 text-white">Email Us</h3>
            <p class="text-gray-200 break-words">
              Inquiries by email<br>
              <a href="mailto:jeremy@airactual.com?subject=Inquiry" class="text-blue-400 hover:underline break-all">info@airactual.com</a>
            </p>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
import ThreeGltf from '~/components/ThreeGltf.vue'
</script>

<style scoped>
/* Custom Font (if not already included) */
@import url('https://fonts.googleapis.com/css2?family=Exo:wght@400;600;700&display=swap');

body {
  font-family: 'Exo', sans-serif;
}

/* Optional: Add smooth transition for background overlay */
.absolute.inset-0 {
  transition: background-opacity 0.3s ease;
}
</style>
