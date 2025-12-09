# 3D Underwater Scene - Sea Navigation

An immersive 3D underwater environment with free navigation where you can explore the ocean depths and swim to the surface to see the sky.

## Features

### 🌊 Underwater Environment
- Detailed ocean floor with realistic terrain
- Animated water surface with wave effects
- Floating particles (bubbles, plankton)
- Swimming fish with circular movement patterns
- Colorful coral formations on the seabed
- Dynamic underwater lighting

### ☀️ Above Water
- Beautiful blue sky
- Realistic sun
- Floating clouds with parallax movement
- Smooth transition between underwater and above-water environments
- Adaptive fog effects

### 🎮 Controls
- **W** - Move forward
- **A** - Move left
- **S** - Move backward
- **D** - Move right
- **SPACE** - Swim up
- **SHIFT** - Swim down
- **MOUSE** - Look around (first-person view)
- **ESC** - Release mouse control

### 📊 UI Features
- Real-time position tracking
- Environment indicator (Underwater/Above Water)
- Depth meter
- Crosshair for navigation

## How to Run

Simply open `index.html` in a modern web browser. No build process or server required!

The scene uses Three.js loaded via CDN, so an internet connection is required for the first load.

## Technical Details

- **Engine**: Three.js (WebGL)
- **Controls**: Pointer Lock Controls for first-person navigation
- **Rendering**: Real-time 3D rendering with dynamic lighting and fog
- **Performance**: Optimized for 60fps with 2000+ particles and 30+ animated objects

## Environment Transitions

The scene dynamically adapts when you cross the water surface:
- **Underwater**: Dark blue tones, dense fog, aquatic lighting
- **Above Water**: Bright sky, clear visibility, natural sunlight

## Browser Compatibility

Works best on modern browsers supporting WebGL 2.0:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
