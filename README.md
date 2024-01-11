# Liquid Masking Project

## Overview
This project creates a visually appealing liquid masking effect using WebGL and shaders. The main components of the project include a canvas, an image, and shaders written in GLSL (OpenGL Shading Language). The shaders are responsible for handling various operations like advection, divergence, pressure, and gradient subtraction, resulting in the dynamic and fluid-like visual effect.

## Project Structure
- **HTML (`index.html`):**
  - Contains the structure of the webpage, including a canvas, an image, and shader scripts.
  - Defines the GLSL shaders as inline scripts with specific IDs.

- **CSS (`style.css`):**
  - Contains styling rules for the HTML elements.
  - Ensures the canvas covers the entire viewport and centers the image with an overlay.

- **JavaScript (`script.js`):**
  - Initializes WebGL and sets up the necessary parameters.
  - Handles user interactions (click, mousemove, touchmove) to simulate fluid splatting on the canvas.
  - Manages the rendering pipeline, including advection, divergence, pressure, and gradient subtraction.
  - Handles resizing of the canvas.

- **GLSL Shaders:**
  1. **Vertex Shader (`vertShader`):**
     - Defines vertex attributes and calculates varying values for neighboring pixels.

  2. **Advection Shader (`fragShaderAdvection`):**
     - Handles the advection process, which simulates the movement of fluid.
     - Uses bilinear interpolation to sample neighboring velocities.

  3. **Divergence Shader (`fragShaderDivergence`):**
     - Computes the divergence of the velocity field, a measure of fluid flow convergence or divergence.

  4. **Pressure Shader (`fragShaderPressure`):**
     - Solves for pressure based on the divergence field using an iterative approach.

  5. **Gradient Subtract Shader (`fragShaderGradientSubtract`):**
     - Subtracts the pressure gradient from the velocity field to enforce incompressibility.

  6. **Splatting Shader (`fragShaderPoint`):**
     - Simulates user interaction by splatting fluid onto the canvas.
     - Modifies the fluid velocity and color based on user input.

  7. **Display Shader (`fragShaderDisplay`):**
     - Handles the final display of the fluid simulation.
     - Allows for custom color manipulation; the example inverts the colors.

## Usage
1. Open `index.html` in a web browser.
2. Observe the interactive fluid simulation created by the shaders.

## Notes
- The project uses WebGL for high-performance graphics rendering.
- The shaders play a crucial role in simulating fluid dynamics, and you can experiment with different parameters and effects by modifying them.
- The image in the center of the canvas is intended for artistic purposes and can be replaced or adjusted as needed.
