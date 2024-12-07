<template>
  <div class="relative min-h-screen bg-gray-900">
    <!-- Three.js Scene Component -->
    <!-- This component renders a Three.js scene as a fixed background layer covering the entire screen -->
    <ThreeTerrain class="fixed inset-0 w-full h-full z-0" />

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
              <div class="mt-5">
                <NuxtLink
                  to="/contact"
                  class="header-button"
                >
                  Get in touch
                </NuxtLink>
              </div>
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

        <section class="main-section-header">
          <div class="one-column-section-inner">
            <h3 class="section-heading">Transforming Data Into Insightful Maps and Solutions</h3>
            <p class="section-paragraph">
              Whether you need precise analyses, custom geospatial tools, 
              or engaging visualizations, we deliver tailored services to 
              help you make informed decisions and communicate effectively.
            </p>
          </div>
        </section>

        <!-- Repeatable Section Template -->
        <section class="repeatable-section">
          <div 
            class="repeatable-section-inner"
          >
            <!-- Left Column -->
            <div class="two-columns-left">
              <h3 class="column-heading">Overlay Analysis</h3>
              <p class="column-paragraph">
                Professional geospatial services are provided to transform raw GPS data 
                into actionable insights. Expertise includes importing and processing GPS 
                survey data, overlaying vector point features on high-resolution 
                orthophotos, and conducting advanced spatial analyses like buffering 
                and intersection for impact assessments. Polished, professional maps 
                with key design elements are created to help visualize and make informed 
                decisions for conservation, planning, or development projects.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/overlay_analysis_buffering.jpg"
                alt="Overlay Analysis Buffering"
                class="landscape-image"
                loading="lazy"
              />
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

        <!-- Repeatable Section Template -->
        <section class="repeatable-section">
          <div 
            class="repeatable-section-inner"
          >
            <!-- Left Column -->
            <div class="two-columns-left">
              <h3 class="column-heading">Digital Elevation Model (DEM) and Surface Analysis</h3>
              <p class="column-paragraph">
                Comprehensive analysis of Digital Elevation Models 
                (DEMs) is conducted to derive valuable insights 
                about terrain and surface features. Tools like 
                ArcGIS Pro are used to examine DEM properties, 
                generate detailed contours, hillshades, slopes, 
                and aspect maps. These analyses provide critical 
                data for applications such as environmental studies, 
                urban planning, and infrastructure development. 
                Surface visualization and terrain-based decision 
                support are tailored to meet project-specific needs.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/dem_surface_analysis.jpg"
                alt="Digital Elevation Model (DEM) and Surface Analysis"
                class="portrait-image"
                loading="lazy"
              />
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
              <h3 class="column-heading">Viewshed Analysis and <br>Visibility Modeling</h3>
              <p class="column-paragraph">
                Detailed viewshed analyses are conducted to model 
                visibility across terrains. Tools like ArcGIS Pro 
                are employed to analyze visibility surfaces, 
                calculate visible areas from base lookout points, 
                and simulate the impact of changes such as increased 
                viewpoint height. These analyses are critical for 
                applications like site planning, communication tower 
                placement, and environmental assessments. Results 
                are compared and optimized to provide actionable 
                insights for strategic planning and decision-making.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/viewshed_analysis.jpg"
                alt="Viewshed Analysis and Visibility Modeling"
                class="portrait-image"
                loading="lazy"
              />
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
              <h3 class="column-heading">Raster Analysis and <br>Site Suitability Mapping</h3>
              <p class="column-paragraph">
                Advanced raster analysis techniques are utilized 
                to evaluate site suitability for various projects, 
                including residential developments. Distance analyses, 
                raster calculator techniques, and raster dataset 
                overlays are applied to identify optimal locations 
                based on specific criteria, such as proximity to 
                infrastructure and elevation constraints. These 
                services offer precise, visually compelling maps 
                designed to streamline decision-making and maximize 
                project success.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/raster_analysis_map_algebra_raster_overlay_for_site_selection_500.jpg"
                alt="Raster Analysis and Site Suitability Mapping"
                class="portrait-image"
                loading="lazy"
              />
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
              <h3 class="column-heading">Geocoding and Address Mapping</h3>
              <p class="column-paragraph">
                Precise geocoding services are available to transform 
                tabular address data into spatially referenced points 
                on a map. Using tools like ArcGIS Pro, tables of 
                addresses or locations are processed to generate 
                accurate, actionable datasets. From preparing data to 
                geocoding addresses, the process ensures seamless 
                integration of location data into GIS projects, making 
                it ideal for urban planning, logistics, and business 
                location analysis.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/geocoding.jpg"
                alt="Geocoding and Address Mapping"
                class="landscape-image"
                loading="lazy"
              />
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
              <h3 class="column-heading">Network Analysis and Route Optimization</h3>
              <p class="column-paragraph">
                Network analyses are performed to determine the 
                shortest or most efficient routes for travel. 
                Tools like ArcGIS Pro are used to create optimized 
                routes, assess the impact of road closures with 
                barriers, and generate detailed turn-by-turn 
                directions. Local network datasets and online 
                network services are leveraged to ensure flexibility 
                and accuracy. These analyses are suited for logistics, 
                emergency response, and urban planning to reduce 
                travel time, lower costs, and improve operational 
                efficiency.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/network_analysis.jpg"
                alt="Network Analysis and Route Optimization"
                class="portrait-image"
                loading="lazy"
              />
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
              <h3 class="column-heading">Map Creation</h3>
              <p class="column-paragraph">
                Comprehensive map creation services encompass 
                designing and organizing projects in ArcGIS Pro, 
                adding and symbolizing layers, and creating 
                professional layouts for clear visualization. 
                Expertise includes calculating distances between 
                locations and exporting maps in various formats. 
                Maps are tailored for presentations, reports, or 
                online use, ensuring they communicate critical 
                spatial information with precision and clarity.
              </p>
            </div>
            <!-- Right Column -->
            <div class="two-columns-right">
              <img
                src="/img/map_creation.jpg"
                alt="Map Creation"
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
