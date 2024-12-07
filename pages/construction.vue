<template>
  <div class="relative min-h-screen bg-gray-900">
    <!-- Three.js Scene Component -->
    <!-- This component renders a Three.js scene as a fixed background layer covering the entire screen -->
    <ThreeGltf class="fixed inset-0 w-full h-full z-0" />

    <!-- Contact Content Overlay -->
    <!-- Overlay container for the main content, positioned relative to the background -->
    <div class="relative flex flex-col items-center justify-start bg-black bg-opacity-0 pt-20">
      <!-- Padding to avoid overlap with fixed header -->

      <!-- Main Content Wrapper -->
      <!-- Wrapper for the content sections with semi-transparent background -->
      <div class="w-full bg-black bg-opacity-50 mb-20">
        <div class="max-w-5xl mx-auto bg-black bg-opacity-0 p-8 rounded-lg w-full mx-4 mb-0">
          
          <!-- Section 1: Introduction -->
          <section class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- Left Column: Text Content -->
            <div class="flex flex-col justify-center p-6">
              <!-- Heading -->
              <h1 class="text-4xl font-exo mb-4 italic text-white">DRONE CONSTRUCTION SERVICES</h1>
              <!-- Description Paragraph -->
              <p class="text-gray-100">
                Top-quality imaging and aerial data using advanced drone technology, helping construction companies improve resource management, decision-making, site progress tracking, safety, and cost savings.
              </p>
              <!-- Call-to-Action Button -->
              <div class="mt-5">
                <NuxtLink
                  to="/contact"
                  class="text-white bg-gnomon-blue inline-block px-8 py-4 rounded-full font-lato hover:bg-blue-700 transition"
                >
                  Get in touch
                </NuxtLink>
              </div>
            </div>
            <!-- Right Column: Placeholder for Image or Additional Content -->
            <div class="flex items-center justify-center pointer-events-auto">
              <!-- Add your image or other content here -->
              <!-- <img src="path-to-your-image.jpg" alt="Description" class="your-classes" /> -->
            </div>
          </section>

        </div>
      </div>
      
      <!-- Additional Content Sections Wrapper -->
      <div class="bg-black bg-opacity-0 p-8 rounded-lg max-w-5xl w-full mx-4">
        
        <!-- Section 2: Overview -->
        <header class="text-left">
          <!-- Section Heading -->
          <h2 class="text-4xl font-exo mb-8 italic text-white text-shadow-[0_4px_8px_rgba(0,0,0,0.5)]">
            Construction Services
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
              <h3 class="column-heading">Drones On Your Job Site</h3>
              <p class="column-paragraph">
                We offer top-tier imaging and aerial data collection using advanced drone 
                technology. Our services enable construction companies to optimize resources, 
                make informed decisions, track site progress, and enhance workplace safety. 
                Stay ahead in the industry by leveraging the latest in aerial data collection 
                to save time and money.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <iframe
              width="100%"
              height="400"
              src="https://www.youtube.com/embed/mVCz41y0-7c?si=UHOOz2E7jqF86ag7"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              allowfullscreen
              class="iframe-video"
              loading="lazy"
            ></iframe>
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
              <h3 class="column-heading">Drone 3D Modeling</h3>
              <p class="column-paragraph">
                While traditional flat maps are useful, our 3D modeling technology takes 
                your project’s visualization to the next level. Overlay current progress 
                with initial blueprints or perform volumetric measurements to achieve your 
                goals. Our detailed and accurate site models are tailored to your project’s 
                specific requirements, enhancing planning and execution.
              </p>
            </div>
            <!-- Right Column -->
            <div class="media-stacked-column">
              <img
              src="/img/litchi_waypoint_mission.png"
              title="Litchi Waypoint Mission"
              class="landscape-image"
              loading="lazy"
            ></img>
              <iframe
                src="https://sketchfab.com/models/79336fac1adf431fb165942740755ec0/embed"
                title="Berkeley Commons South"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen
                class="sketchfab-embed"
                loading="lazy"
              ></iframe>
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
              <h3 class="column-heading">Drone Construction Progression</h3>
              <p class="column-paragraph">
                Regular drone imaging and data capture allow you to track your construction 
                project’s progress over time. Whether weekly or monthly, our services include 
                aerial videos, stills, and data points from consistent locations, helping 
                you monitor timelines and budgets. This visual documentation enhances marketing 
                efforts and demonstrates effective project management.
              </p>
            </div>
            <!-- Right Column -->
            <div class="media-stacked-column">
              <img
              src="/img/litchi_waypoint_mission.png"
              title="Litchi Waypoint Mission"
              class="landscape-image"
              loading="lazy"
            ></img>
              <iframe
                src="https://www.youtube.com/embed/GUqO0v2T4d8"
                title="YouTube video player"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen
                class="iframe-video"
                loading="lazy"
              ></iframe>
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
              <h3 class="column-heading">Drone Site Modeling</h3>
              <p class="column-paragraph">
                From start to finish, Air Actual’s aerial modeling services offer 
                comprehensive views of your site’s progress and final outcome. Our 
                detailed drone-based data collection serves as a compelling marketing 
                tool and supports project planning. Collaborating with licensed surveyors, 
                we ensure data accuracy and compliance, saving you time and money while 
                enhancing safety.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
                <iframe
                src="/qgis_webmap/index.html"
                title="Qgis Webmap"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen
                class="iframe-video"
                loading="lazy"
              ></iframe>
            </div>
          </div>
        </section>

        <!-- Repeatable Section Template -->
        <section class="repeatable-section">
          <div 
            class="repeatable-section-inner-one-column"
          >
            <!-- Left Column -->
            <div class="one-column">
              <h3 class="column-heading">Track the Progress of Your Construction Sites</h3>
              <p class="column-paragraph">
                By using georeferenced orthophotos and 3D data, 
                you and your investors can see the exact status 
                of your project. View the current state of your 
                site for real-time updates, improving on-site 
                management and virtual inspections. Use the 
                slider to compare images taken over six months 
                apart, showcasing changes effectively..
              </p><br>
              <!-- Embedded Iframe (e.g., Before/After Slider) -->
              <iframe
                src="/before_after_slider/index.html"
                title="Before/After Slider"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen
                class="w-full h-[400px] rounded-lg"
                loading="lazy"
              ></iframe>
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
