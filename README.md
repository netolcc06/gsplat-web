# Gaussian Splat Renderer (WebGPU)

Live page: https://netolcc06.github.io/gsplat-web/

A 3D Gaussian Splatting renderer written in C++, compiled to WebAssembly with Emscripten, and
rendering with WebGPU: a compute tile rasterizer (preprocess with EWA projection and spherical
harmonics, GPU radix sort, per-tile binning with tight exact ellipse–tile coverage, and a
shared-memory front-to-back blending kernel with early termination). It is a port of a native
Vulkan renderer. Rendering follows Kerbl et al., *3D Gaussian Splatting for Real-Time Radiance
Field Rendering* (SIGGRAPH 2023).

Needs a browser with WebGPU (current Chrome/Edge; Firefox 141+ on Windows; Safari 26+).
You can open your own `.ply` (standard 3DGS format, optionally `.ply.gz`, plus `cameras.json`);
files are read locally and never leave your browser.

This repository holds the built static site only.

## Demo scene credit

"Knock Community Hall" by [scbenoit](https://superspl.at/user?id=scbenoit)
([source](https://superspl.at/scene/0ff2e6dc)), licensed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Modified: converted from SOG to 3DGS PLY and decimated to 300,000 gaussians with
@playcanvas/splat-transform 3.10.0 — see `demo/knock-community-hall.ATTRIBUTION.txt`.

WebGPU bindings via Emscripten's emdawnwebgpu port (Dawn, BSD-3-Clause).
