# Slide Collage Studio 🖼️📐

> **Intelligent photo collage generator for slides & papers with zero image distortion.**  
> *Vibe coded with Google Antigravity & Gemini 3.8.*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-brightgreen.svg)](https://pages.github.com/)
[![Zero Distortion](https://img.shields.io/badge/Guillotine%20Tree-Zero%20Distortion-teal.svg)]()
[![Export](https://img.shields.io/badge/Export-Lossless%20PNG%20%7C%20Vector%20PDF-purple.svg)]()
[![Built with Antigravity](https://img.shields.io/badge/Built%20with-Google%20Antigravity-4285F4?logo=google&logoColor=white)](https://deepmind.google/)
[![Powered by Gemini 3.8](https://img.shields.io/badge/Powered%20by-Gemini%203.8-8E75C2?logo=googlegemini&logoColor=white)](https://deepmind.google/)

---

## 🔒 100% Private & Client-Side by Design

> ### *"We do not collect, store, or transmit your photos — because architecturally, we cannot."*

* **Zero Backend, Zero Database**: Slide Collage Studio runs as a pure static web application hosted on GitHub Pages. There is no application server, no cloud storage bucket, and no database.
* **In-Memory Browser Processing**: When you import or drag photos into the app, they are decoded purely into your local browser's volatile memory (RAM) via standard HTML5 File & Canvas APIs.
* **Zero Telemetry & Tracking**: There are no tracking cookies, analytics pixels, or background telemetry. Your sensitive photos never leave your device or touch any remote server.
* **Fully Offline-Capable**: Once the page is loaded in your browser, you can disconnect your Internet connection completely and the application will continue to work flawlessly.

---

## 🚀 Launch Live App

Use Slide Collage Studio directly in your web browser — **no installation, no terminal commands, and no accounts required**:

<div align="center">

### 👉 [Open Slide Collage Studio on GitHub Pages](https://<your-username>.github.io/<your-repository-name>/) 👈

*(Replace `<your-username>` and `<your-repository-name>` with your GitHub repository URL once deployed)*

</div>

---

## 🌟 Overview

Arranging multiple heterogeneous images (portrait $9:16$, landscape $16:9$, square $1:1$) onto presentation slides or academic papers usually results in awkward manual resizing, distorted aspect ratios, or wasted whitespace.

**Slide Collage Studio** is a pure client-side web application designed to solve this problem mathematically. Powered by a **Recursive Guillotine Partition Tree** and **Strict 1D Orthogonal Constraints**, it allows you to compose multi-photo layouts with zero distortion, adjust seam proportions effortlessly, and export to **lossless full-resolution PNG** (with alpha transparency) or **tightly-bounded vector PDF** ready for Overleaf LaTeX.

```mermaid
flowchart LR
    A["1. Import Photos<br/>(Heterogeneous Ratios)"] --> B["2. Guillotine Tree<br/>(2D Projection Cuts)"]
    B --> C["3. Metric Solver<br/>(Zero-Distortion Initial Ratio)"]
    C --> D["4. 1D Seam Constraints<br/>(Orthogonal Width/Height Adjust)"]
    D --> E["5. Dynamic Balancing<br/>(Multi-Select Equalize)"]
    E --> F["6. Lossless Export<br/>(Native PNG / Overleaf PDF)"]
```

---

## ✨ Key Features

### 🧩 1. Zero-Distortion Guillotine Layout
* **Automatic 2D Projection Cut**: Identifies natural topological dividers without slicing across photos, adapting to layouts like *1-Left / 2-Right*, *2-Left / 1-Right*, or *4-Grid*.
* **Aspect Ratio Metric Solver**: Solves the global aspect ratio from the leaves up to the root, guaranteeing that the initial layout requires **zero cropping** and causes **zero image squishing**.

### 📏 2. Strict 1D Orthogonal Seam Dragging
* **Vertical Seams (Blue Line)**: Dragging left/right adjusts neighboring column widths independently; vertical row heights are completely locked.
* **Horizontal Seams**: Dragging up/down adjusts row heights while column boundaries remain locked.
* **Adaptive Boundary Grips**: Drag canvas handles (right, bottom, corner) to scale canvas bounds while child tiles automatically adjust proportionally.

### ⚖️ 3. Multi-Select & Perceptual Balancing
* Multi-select photos using `Shift` or `Ctrl` to reveal a floating action toolbar.
* **⬌ Equal Width**: Dynamically computes partition ratios to allocate identical widths to selected items in parallel columns. If items span across different hierarchy levels, it automatically restructures them into a clean vertical column.
* **⬍ Equal Height**: Equates row heights for parallel items, or restructures cross-level photos into a unified horizontal row.
* **Batch Delete**: Remove all selected photos at once or hit the `Delete` key.

### 🔍 4. Independent Per-Photo Zoom & Pan
* **Mouse Wheel Zoom ($100\% - 400\%$)**: Hover over any individual tile and scroll the wheel to zoom into details with a live HUD badge (e.g., `🔍 130%`).
* **Micro-Pan**: Drag inside any photo to adjust visual focal points. Drag friction dynamically scales with zoom level to maintain pinpoint precision.
* **Double-Click Reset**: Double-click any photo (or use the right-click menu) to instantly reset zoom to $100\%$ and center the focal point.

### 🖼️ 5. Lossless Native Resolution Dynamic Export
* **No Artificial Resolution Cap**: Unlike conventional tools that downscale outputs to a fixed 1080p or 2400px canvas, the **Native Resolution Solver** dynamically calculates output dimensions based on the original pixel density of the smallest or dominant photo (supporting 4K, 8K, and 24MP+ images).
* **Live MP & Dimensions Counter**: The sidebar provides a real-time pixel counter and estimated megapixel readout before export.
* **Flexible Resolution Modes**: Choose from *Native 1:1*, *4K UHD (3840px)*, *2K QHD (2560px)*, or *1080P FHD (1920px)*.

### 📄 6. Slide & Academic-Ready Exports
* **Transparent Alpha PNG**: Exports with genuine alpha channels (including rounded corners and gaps), seamlessly blending into PowerPoint, Keynote, or dark-mode slides.
* **Overleaf & Vector PDF Container**: Packages the final composition directly as a standalone PDF document. In academic workflows (such as Overleaf / LaTeX), importing native PDF files often compiles and renders faster than embedding heavy raster image formats. *(Note: This perceived compilation speedup is based on practical user observations and has not been rigorously benchmarked).*

### 🌐 7. Sleek Figma-Inspired UI & Bilingual Toggle
* Distraction-free, minimal aesthetic with zero cluttered paragraphs.
* **One-Click Language Switch**: Click `🌐 繁中 / English` in the top navigation bar to toggle between concise English and Traditional Chinese at any time.

---

## ⌨️ Shortcuts & Controls

| Shortcut / Action | Function |
| :--- | :--- |
| **Mouse Wheel** | Zoom in / out on hovered photo ($100\% \sim 400\%$) |
| **Double-Click** | Reset zoom to $100\%$ and re-center image focus |
| **Click + Drag Photo** | Pan photo focal point inside tile (adaptive friction) |
| **Drag Blue Seams** | Adjust 1D orthogonal column widths or row heights |
| **Shift / Ctrl + Click** | Multi-select multiple photos across canvas or pool |
| **Del / Backspace** | Delete selected photo(s) |
| **Right-Click** | Context menu (Rotate 90°, Replace, Delete, Reset Pan) |
| **Esc** | Close modals, context menu, or clear selections |

---

## 📂 Project Structure

```text
slide-collage-studio/
├── index.html         # Complete single-file application (UI, Canvas, Engine, Export)
├── README.md          # Project documentation (this file)
├── FEATURES.md        # Comprehensive feature documentation & user manual
├── PRINCIPLES.md      # Mathematical formulations, tree topology & solver architecture
├── LICENSE            # MIT License
└── .gitignore         # Excludes local test media, PDFs, and backup files
```

---

## 🛠️ Architecture & Core Principles

For detailed mathematical explanations and layout algorithms:
* Read [`PRINCIPLES.md`](PRINCIPLES.md) to learn how the **Recursive Guillotine Binary Tree**, **1D Orthogonal Constraints**, and **Dynamic Native Resolution Back-propagation** work under the hood.
* Read [`FEATURES.md`](FEATURES.md) for step-by-step user tutorials and edge-case handling.

---

## 💡 Acknowledgements & Vibe Coding

This project was **vibe coded** with [Google Antigravity](https://deepmind.google/) and **Gemini 3.8**, exploring the frontier of agentic pair-programming, recursive guillotine partition trees, and zero-distortion layout geometry.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute it for both personal and commercial slide decks, academic publications, or web integrations.
