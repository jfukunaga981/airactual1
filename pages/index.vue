<template>
  <div>
    <!-- Pop-up element -->
    <div
      id="popUpEl"
      ref="popUpEl"
      class="bg-black bg-opacity-75 fixed px-4 py-2 rounded-lg pointer-events-none z-10"
    >
      <h2 class="text-white text-xs">
        <span id="populationEl" ref="populationEl"></span>
        <span> Population</span>
      </h2>
      <p
        id="populationValueEl"
        ref="populationValueEl"
        class="text-white font-bold text-lg"
      ></p>
    </div>

    <div class="bg-black xl:flex xl:h-[80vh]">
      <div class="xl:w-1/2 flex flex-col justify-center px-8 pt-32 pb-20 xl:pt-0">
        <div class="max-w-lg mx-auto">
          <h1 class="text-white text-4xl mb-8 font-exo leading-none">
            <em>ELEVATE YOUR VIEW WITH DRONE & GIS SERVICES</em>
          </h1>
          <p class="text-neutral-100 mb-8 font-lato">
            Welcome to Air Actual. Delivering unmatched aerial imagery and precise
            geospatial data, empowering you to make informed decisions from a
            higher perspective.
          </p>
          <div>
            <NuxtLink
              to="/contact"
              class="text-white bg-gnomon-blue inline-block px-8 py-4 rounded-full font-lato"
            >
              Get in touch
            </NuxtLink>
          </div>
        </div>
      </div>
      <div class="w-full h-[50vh] xl:w-1/2 xl:h-[90vh] relative" id="canvasContainer">
        <!-- Three.js canvas component -->
        <ThreeScene />
      </div>
    </div>
 
    <!-- New Section: CONTACT US with Three Columns and Two Rows -->
    <div class="gp-section">
      <div class="feature-section">
        <div class="feature-section-inner">
          <header class="section-header">
            <h1 class="section-heading">Aerial and Geospatial Services that Enhance Your Projects</h1>
            <p class="column-paragraph">
              From 4K photography and 360-degree panoramas to precise 
              mapping and GIS integration, our drone technology delivers 
              unique perspectives and actionable insights. Make your 
              visuals stand out and ensure project success with our 
              expert aerial and geospatial services.
            </p>
          </header>
          <section class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- First Column -->
            <div class="feature-card">
              <h3 class="column-heading">📸 Aerial Photography & Videography</h3>
              <p class="column-paragraph">
                Capture breathtaking aerial views with high-resolution images and 4K video. Whether it's for real estate, events, or promotional content, our drone services provide a unique vantage point that sets your visuals apart.<br>
              </p>
            </div>
            <!-- Second Column -->
            <div class="feature-card">
              <h3 class="column-heading">🌐 360-Degree Panoramas</h3>
              <p class="column-paragraph">
                Immerse your clients in a complete visual experience with 360-degree panoramic photography. Crafted with the highest quality standards, our 360-degree photography ensures stunning clarity and exceptional detail that set your projects apart.<br>
              </p>
            </div>
            <!-- Third Column -->
            <div class="feature-card">
              <h3 class="column-heading">🗺️ Photogrammetry & Mapping</h3>
              <p class="column-paragraph">
                Transform aerial images into detailed 2D maps and 3D models with our photogrammetry services. Ideal for construction, land surveying, and environmental monitoring, our precision mapping helps you see the big picture in incredible detail.<br>
              </p>
            </div>
            <!-- Fourth Column -->
            <div class="feature-card">
              <h3 class="column-heading">🌍 GIS Integration</h3>
              <p class="column-paragraph">
                Leverage the power of GIS to analyze and visualize geospatial data. Our GIS services offer comprehensive solutions for urban planning, environmental management, and infrastructure development. We turn complex data into actionable insights.<br>
              </p>
            </div>
            <!-- Fifth Column -->
            <div class="feature-card">
              <h3 class="column-heading">🛠️ Inspections & Surveys</h3>
              <p class="column-paragraph">
                Conduct safe and efficient inspections of hard-to-reach areas. Our drone inspections are perfect for infrastructure, agriculture, and environmental monitoring, providing you with real-time data and high-quality imagery.<br>
              </p>
            </div>
            <!-- Sixth Column -->
            <div class="feature-card">
              <h3 class="column-heading">🏗️ Construction Services</h3>
              <p class="column-paragraph">
                Track your construction project's progress with regular drone imaging. Our weekly or monthly services provide aerial videos, stills, and data, helping you monitor timelines and budgets while enhancing marketing and showcasing project management.<br>
              </p>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import ThreeScene from '~/components/ThreeScene.vue'
</script>

<style scoped>
/* Ensure the pop-up doesn't capture pointer events */
.pointer-events-none {
  pointer-events: none;
}
</style>
