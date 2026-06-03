# Hi there, I'm Isa 👋
<p align="center">
  <img src="assets/Banner.png" alt="A strip of renders from my path tracer, ray tracer, and rasterizers" width="100%">
  <br>
  <em>A few frames from my own Ray Tracer.</em>
</p>

> [!TIP]
> **Open to Graphics / Rendering Programmer roles and internships** (Summer 2026 onward).

## 🎓 About Me
I am a Software Engineering graduate pursuing a **Master's in Games Engineering at WMG, University of Warwick**. I spend most of my time on **real-time rendering** and **computer graphics**: writing renderers, reading papers, and figuring out why the image looks wrong. I play video games too (shocking, I know 🎮), and my ultimate goal is to push the boundaries of visual fidelity as a **Graphics Programmer**.

📄 [**Download my CV**](assets/CV-IsaGeriler.pdf)

## 🔭 Current Focus
I am currently strengthening my foundation in the **Graphics Pipeline**, **C++**, and **DirectX 12 (DX12)**. 

Recently, I was selected for a graphics-focused Master's dissertation under the supervision of **Dr. Thomas Bashford-Rogers**. My current studies and personal projects are dedicated to building the low-level technical groundwork required for this upcoming research.

## 🛠️ Tech Stack
| Category | Technologies |
| :--- | :--- |
| **Languages** | ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white) ![HLSL](https://img.shields.io/badge/HLSL-CC0000?style=flat-square&logo=microsoft&logoColor=white) |
| **Graphics APIs** | ![DirectX 12](https://img.shields.io/badge/DirectX%2012-0078D7?style=flat-square&logo=microsoft&logoColor=white) |
| **Scripting & Processing** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white) |
| **Tools & Profiling** | ![RenderDoc](https://img.shields.io/badge/RenderDoc-black?style=flat-square) ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) |

---

## 🚀 Featured Projects

### [**Path Tracer & Light Transport Engine**](https://github.com/IsaGeriler/RTBase_5749205)
A multithreaded, physically based CPU renderer in C++, built to explore advanced light transport and microfacet models. 

> [!NOTE]
> **Why it matters:** Simulates highly realistic lighting and materials using industry-standard math and data structures, dramatically reducing render times and visual noise through spatial optimizations and Intel AI denoising.

*   **Architecture:** Implements three integrators: Path Tracing, Light Tracing, and Instant Radiosity (which uses a Halton quasi-Monte Carlo sampler relying on prime bases for the Radical Inverse). 
*   **Material Framework:** GGX microfacets (Conductor BSDF, sampled proportionally to the NDF), Plastic (Phong), Diffuse, Oren-Nayar, Glass, Mirror, and a Layered BSDF evaluating Beer's Law for attenuation.
*   **Performance:** Render time and variance are heavily optimized using a **Binned SAH BVH (Surface Area Heuristics Bounding Volume Hierarchy)**, tile-based multithreading, and **Multiple Importance Sampling (MIS)** for latitude-longitude environment maps.
*   **Denoising:** Custom AOV outputs feed directly into **Intel OIDN** for machine-learning-based post-process denoising.

**Tech:** <kbd>C++</kbd> · <kbd>Multithreading</kbd> · <kbd>BVH</kbd> · <kbd>MIS</kbd> · <kbd>PBR Math</kbd> · <kbd>Intel OIDN</kbd>

<p align="center">
  <img src="assets/Kitchen128SPP.png" alt="Kitchen scene, 128 spp path-traced" width="49%">
  <img src="assets/Kitchen16SPPDenoised.png" alt="Kitchen scene, 16 spp denoised with Intel OIDN" width="49%">
</p>
<p align="center"><em>128 spp reference (left) vs. 16 spp denoised with Intel OIDN (right). Achieves comparable fidelity at a fraction of the compute cost.</em></p>

<p align="center">
  <img src="assets/MaterialsScene128SPP.png" alt="Materials test scene showcasing the BSDF framework" width="80%">
</p>
<p align="center"><em>Materials test: GGX conductor, Plastic, Oren-Nayar, Glass, and Mirror BSDFs.</em></p>

---

### [**Optimized Software Rasterizer**](https://github.com/IsaGeriler/WM9M4AssignmentRasterizer5749205)
A CPU implementation of the graphics pipeline, hand-optimized for throughput using hardware-level parallelization (SIMD and multithreading). 

> [!IMPORTANT]
> **Hardware Profiling & The "Thread Plateau"**  
> I profiled how performance scales with thread count on my Intel Core Ultra 7 155H, a hybrid CPU with 6 Performance cores, 8 Efficiency cores, and 2 Low-Power Efficiency cores (16 cores / 22 threads). SIMD (SSE/AVX) plus multithreading gave large early gains, but as shown below the speedup peaks at roughly 2.8x around 6 threads and then degrades. That inflection lines up with the Performance-core count: the first threads land on the fast P-cores, and scaling past them onto the slower E-cores, LP-cores, and hyperthreads adds workers that are both slower and competing for shared resources, so throughput stops improving and starts to regress.

**Tech:** <kbd>C++</kbd> · <kbd>SIMD (SSE/AVX)</kbd> · <kbd>Multithreading</kbd> · <kbd>Performance Profiling</kbd>

<p align="center">
  <img src="assets/Scene3Speedup.png" alt="Graph showing performance plateauing and degrading as thread count increases" width="70%">
</p>
<p align="center"><em>Scene 3 profiling: speedup peaks near the Performance-core count, then degrades as work spills onto slower Efficiency cores and hyperthreads.</em></p>

<p align="center">
  <img src="assets/Scene1.png" alt="Optimized rasterizer, scene 1" width="31%">
  <img src="assets/Scene2.png" alt="Optimized rasterizer, scene 2" width="31%">
  <img src="assets/Scene3.png" alt="Optimized rasterizer, scene 3" width="31%">
</p>

---

### [**DX12Engine (WIP)**](https://github.com/IsaGeriler/DX12Engine)
A modern, custom rendering engine being built from scratch using DirectX 12 to master low-level GPU programming.

> [!NOTE]
> **Why it matters:** Transitioning from CPU rendering to modern, explicit GPU APIs. Focuses on manual memory management, synchronization, and resource binding.

*   **Current Features:** Working through Descriptor Heaps, Root Signatures, and Pipeline State Objects (PSOs). 
*   **Evolution:** This serves as a re-architected, highly scalable improvement over my initial [DirectX 12 Coursework Framework](https://github.com/IsaGeriler/WM9M2Assignment5749205).

**Tech:** <kbd>C++</kbd> · <kbd>HLSL</kbd> · <kbd>DirectX 12</kbd> · <kbd>GPU Memory Management</kbd>

<p align="center">
  <img src="assets/AfterRoughnessMapping.png" alt="DX12 engine, roughness mapping" width="80%">
</p>

---

### [**Offline Ray Tracer (WIP)**](https://github.com/IsaGeriler/RayTracer)
A proving ground for light-transport math based on the *Ray Tracing in One Weekend* (Shirley et al., 2025) architecture. I have extended the base engine to include **Motion Blur** and implemented a custom **Bounding Volume Hierarchy (BVH)** to drastically reduce spatial-intersection costs. The per-pixel render loop and the BVH build are both parallelized using C++17 `std::execution::par` to maximize CPU utilization.

**Tech:** <kbd>C++17</kbd> · <kbd>Ray Tracing</kbd> · <kbd>Motion Blur</kbd> · <kbd>BVH Acceleration</kbd>

<p align="center">
  <img src="assets/RTMB.jpg" alt="Offline ray tracer with motion blur" width="80%">
</p>
<p align="center"><em>Integrated Motion Blur calculation.</em></p>

---

### [**Software Rasterizer (Foundations)**](https://github.com/IsaGeriler/Rasterizer)
An engine built entirely from scratch to deeply understand the math behind graphics APIs. Instead of using existing math libraries (like GLM), I wrote the matrix, vector, and homogeneous coordinate mathematics myself. Implements the full Model-View-Projection (MVP) chain, perspective-correct interpolation, depth buffering (Z-buffer), and Lambertian lighting, parsing `.gem` meshes to render pixel-perfect geometry.

**Tech:** <kbd>C++</kbd> · <kbd>3D Math</kbd> · <kbd>MVP Pipeline</kbd> · <kbd>Z-buffer</kbd>

<p align="center">
  <img src="assets/BunnyShaded.jpg" alt="Stanford bunny, shaded" width="49%">
  <img src="assets/BunnyGeometry.jpg" alt="Stanford bunny, geometry" width="49%">
</p>
<p align="center"><em>Stanford bunny parsed from a .gem mesh: Lambertian shaded (left) and raw geometry (right).</em></p>

---

### [**C++ Client-Server Chat Room**](https://github.com/IsaGeriler/WM9M4AssignmentChatRoom5749205)
A multithreaded networking application showcasing system-level programming outside of graphics. Built a custom client-server architecture using WinSock. The server concurrently handles multiple clients, while the client utilizes a **Dear ImGui** graphical interface. Features include public broadcasting, private 1-to-1 DMs, and real-time **FMOD** audio notifications.

**Tech:** <kbd>C++</kbd> · <kbd>Multithreading</kbd> · <kbd>WinSock (Networking)</kbd> · <kbd>Dear ImGui</kbd> · <kbd>FMOD</kbd>

<p align="center">
  <img src="assets/ChatRoom.png" alt="Dear ImGui chat client" width="80%">
</p>

---

## 📫 Let's Connect
<a href="https://www.linkedin.com/in/isa-geriler/">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
</a>
<a href="mailto:gerilerisaberk@gmail.com">
  <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Personal Email" />
</a>
<a href="mailto:Isa.Geriler@warwick.ac.uk">
  <img src="https://img.shields.io/badge/Warwick_Email-6A329F?style=for-the-badge&logo=microsoft-academic&logoColor=white" alt="Uni Email" />
</a>
