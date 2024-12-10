<template>
  <canvas ref="canvas"></canvas>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import * as THREE from 'three'
import GUI from 'lil-gui'

import heightmap1 from '/img/heightmap1.png'
import heightmap2 from '/img/heightmap2.png'
import heightmap3 from '/img/heightmap3.png'

// Reference to the canvas element
const canvas = ref(null)

// Reference to store GUI instance
let gui = null

// References to store Three.js objects
let scene, camera, renderer, sphere, groundMesh

// Define rotation parameters
let angle = 0; // Current angle for rotation
const rotationSpeed = 0.001; // Speed at which the camera rotates
const radius = 60; // Distance from the center

// Sliders and available maps
const sliders = {
  widthSeg: 200,
  heightSeg: 200,
  horTexture: 1,
  vertTexture: 1,
  dispScale: 15,
  heightMap: heightmap1,
}

const availableMaps = {
  'Mount Diablo': heightmap1,
  'Angel Island': heightmap2,
  'Mount Everest': heightmap3,
}

// Function to create the ground
function createGround() {
  if (groundMesh) {
    scene.remove(groundMesh)
    groundMesh.geometry.dispose()
    groundMesh.material.dispose()
  }

  const groundGeo = new THREE.PlaneGeometry(
    150,
    150,
    sliders.widthSeg,
    sliders.heightSeg
  )
  
  const disMap = new THREE.TextureLoader().load(sliders.heightMap)
  disMap.wrapS = disMap.wrapT = THREE.RepeatWrapping
  disMap.repeat.set(sliders.horTexture, sliders.vertTexture)

  const groundMat = new THREE.MeshStandardMaterial({
    color: 0xffffff,
    wireframe: true,
    displacementMap: disMap,
    displacementScale: sliders.dispScale,
  })

  groundMesh = new THREE.Mesh(groundGeo, groundMat)
  scene.add(groundMesh)
  groundMesh.rotation.x = -Math.PI / 2
}

// Function to update the GUI position based on screen width
function updateGUIPosition() {
  const isMobile = window.innerWidth <= 768; // Checks if this is considered 'mobile'
  const isLandscape = window.innerWidth > window.innerHeight; // Checks if device is in landscape mode

  if (isMobile) {
    if (isLandscape) {
      // Mobile Landscape
      gui.domElement.style.top = 'auto';
      gui.domElement.style.right = '10px';
      gui.domElement.style.bottom = '10px';
    } else {
      // Mobile Portrait
      gui.domElement.style.top = 'auto';
      gui.domElement.style.right = '10px';
      gui.domElement.style.bottom = '25px';
    }
  } else {
    // Larger screens
    gui.domElement.style.top = '100px';
    gui.domElement.style.bottom = 'auto';
    gui.domElement.style.right = '25px';
  }
}

// Animation loop
function animate() {
  // Update the angle for rotation
  angle += rotationSpeed;

  // Calculate new camera position using polar coordinates
  camera.position.x = radius * Math.sin(angle);
  camera.position.z = radius * Math.cos(angle);
  camera.position.y = 10; // Keep the camera at the same height

  // Make the camera look at the center of the scene
  camera.lookAt(0, 0, 0);

  // Render the scene
  renderer.render(scene, camera)
}

// Function to initialize Three.js scene
function initThreeScene() {
  // Initialize Scene
  scene = new THREE.Scene()

  // Initialize Camera
  const aspect = window.innerWidth / window.innerHeight
  camera = new THREE.PerspectiveCamera(75, aspect, 0.1, 1000)
  camera.position.set(radius, 15, 0) // Use the defined radius
  camera.lookAt(0, 0, 0)

  // Initialize Renderer
  renderer = new THREE.WebGLRenderer({ canvas: canvas.value, antialias: true })
  renderer.setSize(window.innerWidth, window.innerHeight)
  renderer.setPixelRatio(window.devicePixelRatio)
  renderer.setAnimationLoop(animate) // Use only setAnimationLoop

  // Add Sphere
  const geometry = new THREE.SphereGeometry(100, 100, 50)
  const material = new THREE.MeshBasicMaterial({
    color: 0xffffff,
    wireframe: true,
    opacity: 0.1,
    transparent: true,
  })
  sphere = new THREE.Mesh(geometry, material)
  scene.add(sphere)

  // Add Lights
  const ambientLight = new THREE.AmbientLight(0xffffff, 0.5)
  scene.add(ambientLight)

  const directionalLight = new THREE.DirectionalLight(0xffffff, 10)
  directionalLight.position.set(10, 10, 10)
  scene.add(directionalLight)

  // Initialize GUI
  gui = new GUI({ title: 'Digital Elevation Models' })

  // Assign the custom class for styling
  gui.domElement.classList.add('custom-lil-gui')

  // Apply initial inline styles
  gui.domElement.style.position = 'fixed';
  gui.domElement.style.zIndex = '10';

  // Set initial position
  updateGUIPosition();

  // Update GUI position on window resize
  window.addEventListener('resize', updateGUIPosition);

  // Position the GUI
  // gui.domElement.style.position = 'absolute'
  // gui.domElement.style.top = '100px'
  // gui.domElement.style.right = '25px'

  // Add Controllers
  // gui.add(sliders, 'widthSeg', 1, 200).name('Width Segments').onChange(createGround)
  // gui.add(sliders, 'heightSeg', 1, 200).name('Height Segments').onChange(createGround)
  // gui.add(sliders, 'horTexture', 1, 10).name('Horizontal Texture').onChange(createGround)
  // gui.add(sliders, 'vertTexture', 1, 10).name('Vertical Texture').onChange(createGround)
  // gui.add(sliders, 'dispScale', 0, 20).name('Displacement Scale').onChange(createGround)
  gui
    .add(sliders, 'heightMap', availableMaps)
    .name('Select Location')
    .onChange(createGround)

  // Initial Ground Creation
  createGround()

  // Handle Window Resize
  window.addEventListener('resize', onWindowResize)
}

// Handle Window Resize
function onWindowResize() {
  const width = window.innerWidth
  const height = window.innerHeight
  camera.aspect = width / height
  camera.updateProjectionMatrix()
  renderer.setSize(width, height)
}

// Clean up resources on unmount
function cleanup() {
  if (gui) {
    gui.destroy()
    gui = null
  }

  window.removeEventListener('resize', onWindowResize)
  window.removeEventListener('resize', updateGUIPosition); // Remove the GUI position event listener

  if (renderer) {
    renderer.dispose()
    renderer.forceContextLoss()
    renderer.context = null
    renderer.domElement = null
    renderer = null
  }

  if (scene) {
    // Dispose all geometries and materials
    scene.traverse((object) => {
      if (object.geometry) object.geometry.dispose()
      if (object.material) {
        if (Array.isArray(object.material)) {
          object.material.forEach((material) => material.dispose())
        } else {
          object.material.dispose()
        }
      }
    })
  }
}

// Lifecycle Hooks
onMounted(() => {
  initThreeScene()
})

onBeforeUnmount(() => {
  cleanup()
})
</script>

<style>
canvas {
  display: block;
}

/* Overall lil-gui panel style */
.custom-lil-gui {
    background-color: rgba(0, 0, 0, 0.8) !important; /* Dark background for the panel */
    color: #fff; /* White text */
    font-family: 'Arial', sans-serif; /* Custom font */
    border: 1px solid #CCCCCC; /* Light gray border */
    border-radius: 8px; /* Rounded corners */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5); /* Subtle shadow for depth */
    padding: 15px; /* Inner spacing */
    opacity: 0.95; /* Slight transparency */
    transition: background-color 0.3s ease, box-shadow 0.3s ease; /* Smooth transitions */
}

/* lil-gui header text style */
.custom-lil-gui .title {
    font-size: 16px;
    font-weight: bold;
    color: #f0f0f0;
    margin-bottom: 10px;
}

/* lil-gui folders (collapsible sections) */
.custom-lil-gui .folder {
    border-top: 1px solid #555;
    margin-top: 10px;
    padding-top: 10px;
}

/* Style the sliders (input[type=range]) */
.custom-lil-gui input[type="range"] {
    width: 100%;
    height: 6px;
    border-radius: 5px;
    background: #444;
    outline: none;
    opacity: 0.8;
    transition: opacity 0.2s;
}

.custom-lil-gui input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 12px;
    height: 12px;
    background: #f0f0f0;
    border-radius: 50%;
    cursor: pointer;
}

.custom-lil-gui input[type="range"]::-moz-range-thumb {
    width: 12px;
    height: 12px;
    background: #f0f0f0;
    border: none;
    border-radius: 50%;
    cursor: pointer;
}

/* Style number input fields */
.custom-lil-gui input[type="number"] {
    background-color: #333;
    color: #fff;
    border: 1px solid #555;
    padding: 4px;
    width: 50px;
    font-size: 12px;
}

/* Style dropdowns (select elements) */
.custom-lil-gui select {
    background-color: #444;
    color: #fff;
    border: 1px solid #555;
    padding: 4px;
    border-radius: 5px;
    font-size: 12px;
    transition: background-color 0.2s ease;
}

/* Customize hover and focus states for dropdown */
.custom-lil-gui select:hover {
    background-color: #555;
}

.custom-lil-gui select:focus {
    border-color: #888;
    outline: none;
}

/* Buttons inside lil-gui */
.custom-lil-gui .button {
    background-color: #333;
    color: #fff;
    border: 1px solid #555;
    border-radius: 5px;
    padding: 5px 10px;
    cursor: pointer;
    text-align: center;
    transition: background-color 0.2s ease;
}

/* Hover effect for buttons */
.custom-lil-gui .button:hover {
    background-color: #555;
}

/* Toggle button (folders) */
.custom-lil-gui .title {
    background-color: #444;
    color: #fff;
    padding: 5px 10px;
    border-radius: 5px;
    font-size: 14px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

/* Hover effect for toggle buttons */
.custom-lil-gui .title:hover {
    background-color: #555;
}

/* Active (open) state of the title tab */
.custom-lil-gui .title.active {
    background-color: #666;
}

/* Labels (text before sliders and inputs) */
.custom-lil-gui label {
    font-size: 12px;
    color: #aaa;
    margin-bottom: 5px;
    display: block;
}

</style>