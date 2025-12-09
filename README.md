# 3D Realistic Underwater Scene - Sea Navigation

An immersive, photorealistic 3D underwater environment with free navigation where you can explore the vibrant ocean depths and swim to the surface to see the sky. Features advanced rendering techniques, volumetric lighting, and charming pixel art fish.

## Features

### 🌊 Advanced Underwater Rendering
- **Realistic Water Surface**: Custom shader with multi-layered waves, Fresnel reflections, sun reflections, and dynamic normals
- **Ocean Floor**: Procedurally generated sandy terrain with multi-octave noise for natural variation
- **Caustics Effects**: Animated light caustics projected on the ocean floor
- **Volumetric God Rays**: Beautiful light shafts piercing through the water
- **Depth-Based Fog**: Visibility decreases naturally with depth
- **Post-Processing**: Bloom effects, underwater color grading, subtle chromatic aberration

### 🐠 Pixel Art Marine Life
- **75 Voxel-Style Fish**: Charming blocky fish constructed from cubes
- **5 Fish Schools**: Coordinated schooling behavior with 15 fish per school
- **Animated Swimming**: Realistic tail wagging and body movement
- **Diverse Colors**: Randomly generated vibrant color schemes
- **Detailed Features**: Eyes with pupils, dorsal fins, pectoral fins, decorative scales

### 🌿 Rich Underwater Flora
- **60 Kelp Plants**: Tall, swaying kelp forest with animated movement
- **40 Coral Reefs**: Brain coral, branching coral, and glowing polyps
- **80 Rocks & Boulders**: Irregular, natural-looking rock formations
- **Varied Vegetation**: Multiple species with different colors and shapes

### ✨ Advanced Particle Systems
- **1000 Bubbles**: Rising bubbles with circular textures and realistic movement
- **1500 Plankton**: Glowing particles drifting with ocean currents
- **Dynamic Behavior**: Particles loop naturally and respond to water boundaries

### ☀️ Realistic Sky & Atmosphere
- **Gradient Sky Shader**: Atmospheric perspective from horizon to zenith
- **Realistic Sun**: Bright sun with glowing halo effect
- **30 Volumetric Clouds**: Puffy, detailed clouds with individual particle composition
- **Dynamic Cloud Movement**: Clouds drift across the sky at varying speeds

### 💡 Advanced Lighting System
- **Directional Sun**: 2048x2048 shadow maps with soft shadows
- **Hemisphere Light**: Natural sky/ground ambient lighting
- **Multiple Underwater Lights**: 5 animated point lights at various depths
- **Shadow Casting**: Fish, coral, and kelp cast realistic shadows
- **Depth-Based Light Attenuation**: Light intensity decreases with depth

### 🎮 Controls
- **W** - Move forward
- **A** - Move left
- **S** - Move backward
- **D** - Move right
- **SPACE** - Swim up
- **SHIFT** - Swim down
- **MOUSE** - Look around (first-person view)
- **ESC** - Release mouse control

### 📊 Enhanced UI Features
- Real-time position tracking (X, Y, Z coordinates)
- Environment indicator (Underwater/Above Water)
- Depth meter in meters
- Light level percentage (decreases with depth)
- Stylized crosshair with glow effect
- Smooth backdrop blur on UI elements

## How to Run

Simply open `index.html` in a modern web browser. No build process or server required!

The scene uses Three.js loaded via CDN, so an internet connection is required for the first load.

## Technical Details

### Graphics Engine
- **Engine**: Three.js r160 (WebGL 2.0)
- **Renderer**: WebGLRenderer with antialiasing and high-performance mode
- **Tone Mapping**: ACES Filmic for cinematic color grading
- **Shadow Maps**: PCF soft shadows at 2048x2048 resolution

### Post-Processing Pipeline
- **Effect Composer**: Multi-pass post-processing
- **Unreal Bloom Pass**: Adjustable bloom for glowing effects
- **Custom Underwater Shader**: Color grading, chromatic aberration, depth effects

### Shaders
- **Water Shader**: Custom GLSL vertex/fragment shaders with:
  - Multi-frequency wave generation
  - Dynamic normal calculation
  - Fresnel reflection
  - Specular sun reflection
- **Sky Shader**: Gradient atmosphere with exponential falloff
- **Underwater Pass**: Color tinting and optical effects

### Performance
- **Frame Rate**: Optimized for 60fps
- **Object Count**: 200+ objects (fish, coral, kelp, rocks)
- **Particle Count**: 2500+ particles
- **Draw Calls**: Efficiently batched with geometry instancing
- **Culling**: Frustum culling for off-screen objects

### Art Style
- **Fish**: Pixel/voxel art style with flat shading for retro charm
- **Environment**: Realistic PBR materials with proper roughness/metalness
- **Lighting**: Physically-based with multiple light sources
- **Particles**: Additive blending for glowing effects

## Environment Transitions

The scene dynamically adapts when you cross the water surface (y = 0):

### Underwater (y < 0)
- Dark blue-tinted color grading
- Dense exponential fog (increases with depth)
- Visible god rays and caustics
- Multiple underwater point lights
- Chromatic aberration
- Reduced bloom intensity
- Light level indicator shows depth attenuation

### Above Water (y > 0)
- Clear sky blue background
- Minimal fog for atmospheric haze
- Bright sunlight and clouds visible
- God rays and caustics hidden
- No color tinting
- Enhanced bloom for sky glow
- Light level at 100%

## Browser Compatibility

Requires a modern browser with WebGL 2.0 support:
- **Chrome 90+** (Recommended)
- **Firefox 88+**
- **Safari 14+**
- **Edge 90+**

### Minimum Requirements
- WebGL 2.0 support
- 4GB RAM
- Dedicated GPU recommended for optimal performance

### Recommended Specs
- Modern GPU (GTX 1060 / RX 580 or better)
- 8GB RAM
- 1080p display or higher

## Credits

Built with Three.js - https://threejs.org/

Advanced rendering techniques inspired by real-time ocean rendering research and modern game engines.
