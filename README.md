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

#### Keyboard Controls
- **W** - Move forward
- **A** - Move left
- **S** - Move backward
- **D** - Move right
- **SPACE** - Swim up
- **SHIFT** - Swim down
- **MOUSE** - Look around (first-person view)
- **ESC** - Release mouse control

#### 🎥 Gesture Controls (Camera-Based)
- **✋ Hand Up** (palm forward, fingers extended) - Swim forward to catch fish
- **👍 Thumbs Up** - Rise above the sea surface
- Click "Enable Gesture Control" button to activate camera
- Gesture controls work alongside keyboard controls
- Real-time visual feedback with hand tracking overlay

### 🧜 Fish Man Avatar
- **Visible First-Person Arms**: See your webbed fish-man hands while swimming
- **Fish-Human Hybrid Design**: Blue scaled skin with metallic sheen
- **Webbed Hands**: Three fingers with transparent webbing between them
- **Decorative Scales**: Shimmering fish scales along the arms
- **Dynamic Animations**:
  - Idle swimming motion with gentle arm movement
  - Forward reaching when hand-up gesture detected
  - Upward stroking when thumbs-up gesture detected
  - Smooth transitions between animation states

### 🤖 AI-Powered Gesture Recognition
- **MediaPipe Hands Integration**: Google's state-of-the-art hand tracking
- **Real-Time Detection**: 30fps hand landmark tracking
- **Visual Feedback**: Live camera feed with skeletal hand overlay
- **Two Gesture Types**:
  - Hand Up: Open palm facing camera, fingers extended upward
  - Thumbs Up: Thumb extended upward, other fingers curled
- **Privacy-Focused**: All processing happens locally in browser
- **Camera Feed**: 320x240 overlay in bottom-right corner
- **Status Indicator**: Shows current detected gesture with color coding

### 📊 Enhanced UI Features
- Real-time position tracking (X, Y, Z coordinates)
- Environment indicator (Underwater/Above Water)
- Depth meter in meters
- Light level percentage (decreases with depth)
- Gesture status display with visual feedback
- Camera feed overlay with hand tracking
- Stylized crosshair with glow effect
- Smooth backdrop blur on UI elements
- Toggle button for gesture control activation

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

### Gesture Recognition System
- **Library**: MediaPipe Hands v0.4
- **Hand Tracking**: Up to 2 hands simultaneously
- **Landmark Detection**: 21 3D landmarks per hand
- **Processing**: Client-side inference (no data sent to servers)
- **Algorithms**:
  - Hand Up: Checks all fingers extended + palm forward + wrist position
  - Thumbs Up: Thumb extended + other fingers curled + hand horizontal
- **Integration**: Gesture input combined with keyboard controls using normalized vectors

### Performance
- **Frame Rate**: Optimized for 60fps (3D scene) + 30fps (gesture tracking)
- **Object Count**: 200+ objects (fish, coral, kelp, rocks) + fish man avatar
- **Particle Count**: 2500+ particles
- **Draw Calls**: Efficiently batched with geometry instancing
- **Culling**: Frustum culling for off-screen objects
- **Camera Processing**: Separate thread for gesture recognition
- **Gesture Latency**: <50ms from hand movement to action

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
- **Chrome 90+** (Recommended - best MediaPipe support)
- **Firefox 88+**
- **Safari 14+**
- **Edge 90+**

### Minimum Requirements
- WebGL 2.0 support
- 4GB RAM
- Dedicated GPU recommended for optimal performance
- **Webcam** (optional, for gesture controls)
- Camera permissions granted in browser

### Recommended Specs
- Modern GPU (GTX 1060 / RX 580 or better)
- 8GB RAM
- 1080p display or higher
- 720p webcam for gesture recognition

### Camera Requirements (Gesture Control)
- Webcam access must be allowed when prompted
- Minimum 480p resolution
- Works with built-in laptop cameras or external USB webcams
- Good lighting recommended for accurate hand tracking
- Gesture control is optional - keyboard controls always available

## Credits

**Built with:**
- [Three.js](https://threejs.org/) - 3D rendering engine
- [MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands.html) - Hand tracking and gesture recognition by Google

**Techniques:**
- Advanced rendering techniques inspired by real-time ocean rendering research and modern game engines
- Gesture recognition algorithms based on hand landmark geometry
- Fish man avatar design inspired by aquatic mythology and pixel art aesthetics

**Special Thanks:**
- MediaPipe team for open-source hand tracking
- Three.js community for excellent WebGL framework
- Real-time graphics researchers for water rendering techniques
