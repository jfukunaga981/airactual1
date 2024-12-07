<template>
  <div class="relative min-h-screen bg-gray-900">
    <!-- Three.js Scene Component -->
    <!-- This component renders a Three.js scene as a fixed background layer covering the entire screen -->
    <ThreeSun class="fixed inset-0 w-full h-full z-0" />

    <!-- Contact Content Overlay -->
    <!-- Overlay container for the main content, positioned relative to the background -->
    <div class="relative flex flex-col items-center justify-start bg-black bg-opacity-0 pt-[62px]">
      <!-- Padding to avoid overlap with fixed header -->

      <!-- Main Content Wrapper -->
      <!-- Wrapper for the content sections with semi-transparent background -->
      <div class="header-fullwidth-container">
        <div class="header-section">
          <div class="header-section-inner">
            <div class="header-section-left">
              <h1 class="header-section-heading">GEOGRAPHIC INFORMATION SYSTEMS</h1>
              <p class="section-paragraph">
                Turning complex spatial data into clear, actionable insights through 
                advanced GIS solutions, interactive mapping, and professional 
                cartographic design.
              </p>
            </div>
            <div class="header-section-right">
              <!-- Add your image or other content here -->
              <!-- <img src="path-to-your-image.jpg" alt="Description" class="your-classes" /> -->
            </div>
          </div>
        </div>
      </div>
      
      <!-- Additional Content Sections Wrapper -->
      <div class="bg-black bg-opacity-0 p-8 rounded-lg max-w-5xl w-full mx-4">

        <!-- Section 2: Overview -->
        <header class="text-left">
          <!-- Section Heading -->
          <h2 class="text-4xl font-exo mb-8 italic text-white text-shadow-[0_4px_8px_rgba(0,0,0,0.5)]">
            Contact
          </h2>
          <!-- Optional Subheader Content -->
        </header>

        <!-- Repeatable Section Template -->
        <section class="repeatable-section">
          <div 
            class="repeatable-section-inner"
          >
            <!-- Left Column -->
            <div class="two-columns-left">
              <h3 class="column-heading">Get in touch</h3>
              <p class="column-paragraph">
                Reach out by phone, text, or email. We're standing by to help you with 
                service inquiries, customer service, or just general questions.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
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
          </div>
        </section>

        <!-- Repeatable Section Template -->
        <section class="repeatable-section">
          <div 
            class="repeatable-section-inner"
          >
            <!-- Left Column -->
            <div class="two-columns-left">
              <h3 class="column-heading">Geodatabase Design & <br>Relationship Management</h3>
              <p class="column-paragraph">
                Efficient geospatial data organization and relationships 
                are achieved through the development and management of 
                geodatabases. Services include creating structured 
                attribute tables, establishing robust relationships 
                between feature classes and associated tables, and 
                updating metadata to maintain data integrity. Tools 
                like ArcGIS Pro are utilized to optimize data 
                structures, enhancing geospatial analysis and 
                streamlining project workflows. Whether designing 
                new geodatabases or enhancing existing data, 
                solutions ensure readiness for accurate and 
                effective decision-making.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/data_structure_and_relationships.jpg"
                alt="Geodatabase Design & Relationship Management"
                class="landscape-image"
                loading="lazy"
              />
            </div>
          </div>
        </section>

      </div>
    </div>
  </div>
</template>

<script setup>
// Importing the Three.js scene component
import ThreeGltf from '~/components/ThreeGltf.vue'
</script>

<style scoped>
/* Import custom fonts from Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Exo:wght@400;600;700&display=swap');

/* Apply the custom font to the body */
body {
  font-family: 'Exo', sans-serif;
}

/* Smooth transition effect for background opacity changes */
.relative {
  transition: background-opacity 0.3s ease;
}
</style>