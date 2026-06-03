# Hi there, I'm Isa 👋
<p align="center">
  <a href="https://ryu-ga-gotoku.com/kiwami3/">
    <img src="https://github.com/user-attachments/assets/74ef9bc8-91a4-4be3-99ea-10ba9a6cbceb" alt="Kiryu and Mine Banner" width="100%">
  </a>
  <br>
  <em>"変わる伝説、新たな歴史 - The Legend Evolves, A New History Begins."</em>
</p>

> 🔎 **Open to Graphics / Rendering Programmer roles and internships** (Summer 2026 onward).

## 🎓 About Me
I am a Software Engineering graduate pursuing a **Master's in Games Engineering at WMG, University of Warwick**. I spend most of my time on **real-time rendering** and **computer graphics**: writing renderers, reading papers, and working out why the image looks wrong. I like video games too (surprise, Sherlock 🕵️‍♂️), and I'm aiming to specialize as a **Graphics Programmer**.

📄 [**Download my CV**](assets/CV-IsaGeriler.pdf)

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

---

### [**Path Tracer & Light Transport Engine**](https://github.com/IsaGeriler/RTBase_5749205)
A multithreaded, physically based CPU renderer in C++, built to explore advanced light transport and microfacet models.

- Three integrators in one architecture: **Path Tracing**, **Instant Radiosity**, and **Light Tracing**. Instant Radiosity uses a Halton quasi-Monte Carlo sampler relying on prime bases for the Radical Inverse.
- Material framework: GGX microfacets (Conductor BSDF, sampled proportionally to the NDF), Plastic (Phong model), Oren-Nayar, and a Layered BSDF that evaluates Beer's Law for attenuation.
- Render time and variance managed with a **Binned SAH BVH**, tile-based rendering, and **Multiple Importance Sampling** for latitude-longitude environment maps (luminance-based PDF).
- Custom AOV outputs feed **Intel OIDN** for post-process denoising.

**Tech:** C++ · Path Tracing · Instant Radiosity · SAH BVH · MIS · GGX / Layered BSDFs · Intel OIDN

<p align="center">
  <img src="assets/Kitchen128SPP.png" alt="Kitchen scene, 128 spp path-traced" width="48%">
  <img src="assets/Kitchen16SPPDenoised.png" alt="Kitchen scene, 16 spp denoised with Intel OIDN" width="48%">
</p>
<p align="center"><em>Kitchen scene: 128 spp reference (left) vs. 16 spp denoised with Intel OIDN (right).</em></p>
<p align="center">
  <img src="assets/MaterialsScene128SPP.png" alt="Materials test scene showcasing the BSDF framework" width="80%">
</p>
<p align="center"><em>Materials test: GGX conductor, Plastic, Oren-Nayar, Glass, and Mirror BSDFs.</em></p>

---

### [**Optimized Software Rasterizer**](https://github.com/IsaGeriler/WM9M4AssignmentRasterizer5749205)
A CPU implementation of the graphics pipeline, hand-optimized for throughput with SIMD and multithreading.

**Tech:** C++ · SIMD (SSE/AVX/AVX2) · Multithreading

<p align="center">
  <img src="assets/Scene1.png" alt="Optimized rasterizer, scene 1" width="32%">
  <img src="assets/Scene2.png" alt="Optimized rasterizer, scene 2" width="32%">
  <img src="assets/Scene3.png" alt="Optimized rasterizer, scene 3" width="32%">
</p>

---

### [**Offline Ray Tracer (WIP)**](https://github.com/IsaGeriler/RayTracer)
An ongoing multithreaded CPU ray tracer in C++, and a proving ground for light-transport math. It implements the full *Ray Tracing in One Weekend* (Shirley et al., 2025) architecture and extends into book two with integrated Motion Blur and a custom Bounding Volume Hierarchy (BVH) to drop spatial-intersection costs. The BVH build is parallelized via C++17 `std::execution::par` to keep the CPU fed, and I'm working through the rest of the trilogy to build out the full feature set.

**Tech:** C++ · Ray Tracing · Motion Blur · Custom BVH · std::execution::par

<p align="center">
  <img src="assets/RTMB.jpg" alt="Offline ray tracer with motion blur" width="80%">
</p>
<p align="center"><em>Motion blur, integrated from book two.</em></p>

---

### [**Software Rasterizer (Legacy)**](https://github.com/IsaGeriler/Rasterizer)
An earlier rasterizer implementing the full Model-View-Projection (MVP) transformation chain, perspective-correct interpolation, depth buffering, and Lambertian lighting, all on a math library written from scratch (matrices, vectors, and homogeneous coordinates). Parses .gem mesh files and renders with pixel-perfect rasterization.

**Tech:** C++ · Rasterization · MVP Pipeline · Perspective-Correct Interpolation · Z-buffer

<p align="center">
  <img src="assets/BunnyShaded.jpg" alt="Stanford bunny, shaded" width="48%">
  <img src="assets/BunnyGeometry.jpg" alt="Stanford bunny, geometry" width="48%">
</p>
<p align="center"><em>Stanford bunny parsed from a .gem mesh: shaded (left) and geometry (right).</em></p>

---

### [**Chat Room**](https://github.com/IsaGeriler/WM9M4AssignmentChatRoom5749205)
A client-server chat application built from scratch using WinSock for networking. The server handles multiple clients concurrently, while the client features a graphical interface built with Dear ImGui, supporting public broadcast messages and private 1-to-1 direct messages (DMs). FMOD integration provides real-time sound notifications for incoming messages.

**Tech:** C++ · WinSock · Dear ImGui · FMOD

<p align="center">
  <img src="assets/ChatRoom.png" alt="Dear ImGui chat client" width="80%">
</p>

---

### [**DX12Engine (WIP)**](https://github.com/IsaGeriler/DX12Engine)
A custom rendering engine built from scratch using DirectX 12.

- **Goal:** To master low-level concepts including Descriptor Heaps, Root Signatures, and Pipeline State Objects (PSOs).
- **Evolution:** This will be the re-architected and improved version of my previous framework ([Coursework Submission](https://github.com/IsaGeriler/WM9M2Assignment5749205)).

**Tech:** C++ · DirectX 12 · Descriptor Heaps · Root Signatures · PSOs

<p align="center">
  <img src="assets/AfterRoughnessMapping.png" alt="DX12 engine, roughness mapping" width="80%">
</p>

---

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
