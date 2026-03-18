# 🚀 Key Features

- Pascal-Optimized Stack: Tailored for NVIDIA GTX 1050, utilizing CUDA 12.1 and specialized PyTorch 2.6 builds to maximize the compute capabilities of the Pascal microarchitecture.
- VRAM Management: Pre-configured for low-VRAM environments, ensuring Stable Diffusion 1.5 and SDXL Turbo can run without out-of-memory (OOM) errors.
- Containerized Portability: Fully orchestrated via Docker Compose, abstracting complex GPU driver layers and library dependencies for immediate "up-and-run" capability.
- Integrated Monitoring: Features a dedicated TensorBoard service to visualize generation metrics and resource utilization in real-time.
- Modern AI Ecosystem: Includes transformers, accelerate, and safetensors, providing a production-ready toolkit for generative research.

# 📂 Project Structure

- _pytorch_stablediffusion_image_studio.ipynb: The research core, containing logic for memory-efficient pipe initialization and image generation.
- Dockerfile: Defines the Python 3.10 environment, ensuring compatibility between the CUDA 12.2 runtime and the GTX 1050 hardware.
- docker-compose.yml: Manages the multi-container setup, handles GPU device reservations, and mounts persistent storage for models and outputs.
- requirements.txt: Strict versioning for the PyTorch 2.6+cu121 ecosystem.

# 🛠️ Quick Start

## 1. Requirements  
   - Hardware: NVIDIA GTX 1050 (Pascal) or higher.  
   - Software: Docker + NVIDIA Container Toolkit.

## 2. Launch
```bash
docker-compose up -d
```
## 3. Access

- 📓 **Studio (JupyterLab):** [http://localhost:4040](http://localhost:4040)  
- 📊 **Metrics (TensorBoard):** [http://localhost:6008](http://localhost:6008)

---

## ⚙️ Technical Specifications

| Component        | Version / Specification              |
|------------------|--------------------------------------|
| GPU Architecture | NVIDIA Pascal (GTX 1050)             |
| PyTorch          | 2.6.0 + cu121                        |
| CUDA Runtime     | 12.2 / 12.1                          |
| Base Image       | Ubuntu 22.04                         |
| Memory Tuning    | Attention Slicing & CPU Offload      |