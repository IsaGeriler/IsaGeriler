# Hi there, I'm Isa 👋
<p align="center">
  <a href="https://ryu-ga-gotoku.com/kiwami3/">
    <img src="https://github.com/user-attachments/assets/74ef9bc8-91a4-4be3-99ea-10ba9a6cbceb" alt="Kiryu and Mine Banner" width="100%">
  </a>
  <br>
  <em>"変わる伝説、新たな歴史 - The Legend Evolves, A New History Begins."</em>
</p>

## 🎓 About Me
I am a Software Engineering graduate currently pursuing a **Master's in Games Engineering at WMG, University of Warwick**.

Passionate about video games (surprise, Sherlock 🕵️‍♂️), **real-time rendering**, **computer graphics**, and the math behind the pixels. My goal is to specialize as a Graphics Programmer, bridging the gap between artistic vision and hardware performance.

## 🔭 Current Focus
Currently, I am strengthening my foundation in the **Graphics Pipeline**, **C++**, and **DirectX 12 (DX12)**.

Recently, I was selected for a graphics-focused Master's dissertation under the supervision of **Dr. Thomas Bashford-Rogers**. My current studies are dedicated to building the technical groundwork required for this upcoming research.

## 🛠️ Tech Stack
| Category | Technologies |
| :--- | :--- |
| **Languages** | ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white) ![HLSL](https://img.shields.io/badge/HLSL-CC0000?style=flat-square&logo=microsoft&logoColor=white) |
| **Graphics API** | ![DirectX 12](https://img.shields.io/badge/DirectX%2012-0078D7?style=flat-square&logo=microsoft&logoColor=white) |
| **Scripting & Processing** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white) |
| **Tools & Version Control** | ![RenderDoc](https://img.shields.io/badge/RenderDoc-black?style=flat-square) ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) |

## 🚀 Featured Projects
Here are some of the projects I'm proud of:

### [**Path Tracer & Light Transport Engine**](https://github.com/IsaGeriler/RTBase_5749205)
*An extended, CPU-based multithreaded, Physically Based Renderer written in C++, built to explore advanced light transport and microfacet models. The core architecture supports standard Path Tracing alongside Instant Radiosity and Light Tracing integrators. For the Instant Radiosity implementation, Halton Sampler (a quasi-Monte Carlo sampler) is utilized, relying on prime bases for the Radical Inverse. The material framework handles GGX Microfacets (Conductor BSDF, sampled proportionally to the NDF), Plastic BSDF (using Phong model), Oren-Nayar BSDF, and Layered BSDF which evaluating Beer's Law for attenuation. Render times and variance are managed via a Binned SAH BVH, tile-based rendering, Multiple Importance Sampling (MIS) for Latitude-Longitude based Environment Maps (utilizing a luminance-based PDF), and custom AOV outputs to support Intel OIDN for denoising (post-processing).*

<p align="center">
  <img src="assets/Kitchen128SPP.png" alt="Kitchen scene, 128 spp path-traced" width="48%">
  <img src="assets/Kitchen16SPPDenoised.png" alt="Kitchen scene, 16 spp denoised with Intel OIDN" width="48%">
</p>
<p align="center"><em>Kitchen scene: 128 spp reference (left) vs. 16 spp denoised with Intel OIDN (right).</em></p>
<p align="center">
  <img src="assets/MaterialsScene128SPP.png" alt="Materials test scene showcasing the BSDF framework" width="80%">
</p>
<p align="center"><em>Materials test: GGX conductor, Plastic, Oren-Nayar, Glass, and Mirror BSDFs.</em></p>

### [**Optimized Software Rasterizer**](https://github.com/IsaGeriler/WM9M4AssignmentRasterizer5749205)
*A CPU-based implementation of the graphics pipeline, accelerated using optimization techniques and multithreading.*
- **Tech:** C++, SIMD (SSE/AVX, AVX2), Multi-threading

<p align="center">
  <img src="assets/Scene1.png" alt="Optimized rasterizer, scene 1" width="32%">
  <img src="assets/Scene2.png" alt="Optimized rasterizer, scene 2" width="32%">
  <img src="assets/Scene3.png" alt="Optimized rasterizer, scene 3" width="32%">
</p>

### [**Offline Ray Tracer (WIP)**](https://github.com/IsaGeriler/RayTracer)
*An ongoing multithreaded offline ray tracer (CPU-based), written in C++, acting as a proving ground for light transport math. Currently encompasses the full Ray Tracing in One Weekend (Shirley et al., 2025) architecture, extending into book two with integrated Motion Blur and a custom Bounding Volume Hierarchy (BVH) to drop spatial intersection costs. The BVH build is parallelized utilizing C++17 executions (std::execution::par) to keep the CPU fed. Actively working through the rest of the trilogy to build out the full advanced feature set.*

<p align="center">
  <img src="assets/RTMB.jpg" alt="Offline ray tracer with motion blur" width="80%">
</p>
<p align="center"><em>Motion blur, integrated from book two.</em></p>

### [**Software Rasterizer (Legacy)**](https://github.com/IsaGeriler/Rasterizer)
*Earlier implementation of rasterization techniques. Implements the full Model-View-Projection (MVP) transformation chain, perspective-correct interpolation, depth buffering, and Lambertian lighting using a math library written from scratch, for matrices, vectors, and homogeneous coordinates. Parses .gem mesh files and renders with pixel-perfect rasterization.*

<p align="center">
  <img src="assets/BunnyShaded.jpg" alt="Stanford bunny, shaded" width="48%">
  <img src="assets/BunnyGeometry.jpg" alt="Stanford bunny, geometry" width="48%">
</p>
<p align="center"><em>Stanford bunny parsed from a .gem mesh: shaded (left) and geometry (right).</em></p>

### [**Chat Room**](https://github.com/IsaGeriler/WM9M4AssignmentChatRoom5749205)
*A client-server chat room application built from scratch using WinSock for networking. The server handles multiple clients concurrently, while the client features a graphical interface built with Dear ImGui. Supports public broadcast messages and private 1-to-1 direct messages (DMs). FMOD integration provides real-time sound notifications for incoming messages.*

<p align="center">
  <img src="assets/ChatRoom.png" alt="Dear ImGui chat client" width="80%">
</p>

### [**DX12Engine (WIP)**](https://github.com/IsaGeriler/DX12Engine)
*A custom rendering engine built from scratch using DirectX 12.*
- **Goal:** To master low-level concepts including Descriptor Heaps, Root Signatures, and Pipeline State Objects (PSOs).
- **Evolution:** This will be the re-architected and improved version of my previous framework ([Coursework Submission](https://github.com/IsaGeriler/WM9M2Assignment5749205)).

<p align="center">
  <img src="assets/AfterRoughnessMapping.png" alt="DX12 engine, roughness mapping" width="80%">
</p>

## 📫 Let's Connect
<a href="https://www.linkedin.com/in/isa-berk-geriler/">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
</a>
<a href="mailto:gerilerisaberk@gmail.com">
  <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Personal Email" />
</a>
<a href="mailto:Isa.Geriler@warwick.ac.uk">
  <img src="https://img.shields.io/badge/Warwick_Email-6A329F?style=for-the-badge&logo=microsoft-academic&logoColor=white" alt="Uni Email" />
</a>

<!--
**IsaGeriler/IsaGeriler** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
