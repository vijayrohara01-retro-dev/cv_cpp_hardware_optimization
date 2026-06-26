# Computer Vision: C++ Hardware Kernel Optimization

> **Note on Portfolio:** *This repository is part of a curated public portfolio showcasing standalone technical concepts. The majority of my consulting work involves proprietary client architecture, embedded systems, and is bound by strict NDAs, and therefore remains private.*

## Project Overview
When deploying computer vision models on edge hardware, pure Python implementations often introduce severe CPU to GPU latency. This project demonstrates how to bypass Python overhead by writing a custom C++ kernel to handle low level array manipulation, compiling it as a shared library, and seamlessly integrating it back into the Python CV pipeline.

## Technical Approach
1. **Low Level Optimization:** A custom C++ kernel (`edge_kernel.cpp`) is written to handle pixel by pixel intensity capping, simulating hardware level image optimization.
2. **Compilation:** The kernel is compiled into a shared library (`libedge.so`).
3. **Interoperability:** **OpenCV** is used to ingest and flatten an image array, which is then passed directly to the C++ kernel in memory using Python's **ctypes**. 

This decoupled architecture maintains Python's ease of use for high level routing while leveraging C++ for computationally expensive operations.

## Tech Stack
* **Languages:** C++, Python
* **Computer Vision:** OpenCV
* **Interoperability:** C Types
