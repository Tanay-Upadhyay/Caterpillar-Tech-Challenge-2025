### **👁️ LiteDepth: Real-Time 3D Perception for Industrial Safety**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-27A4DE?style=for-the-badge&logo=opencv&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/-Raspberry%20Pi-C51A4A?style=for-the-badge&logo=raspberry-pi)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)

An end-to-end edge AI perception system that enhances operator safety by fusing real-time object detection with metric depth estimation, all running on a low-power device. This project was a finalist at the **Caterpillar Hackathon**.

### 📜 **Table of Contents**

*   [💡 The Idea: From Seeing to Understanding](#-the-idea-from-seeing-to-understanding)
*   [💼 Why This Project Matters: Solving Critical Safety Gaps](#-why-this-project-matters-solving-critical-safety-gaps)
*   [🚀 Tech Stack & Architecture](#-tech-stack--architecture)
*   [✨ Key Features](#-key-features)
*   [🖼️ Visual Showcase: The LiteDepth System in Action](#️-visual-showcase-the-litedepth-system-in-action)
*   [📂 Project Structure](#-project-structure)
*   [🏁 Getting Started](#-getting-started)
    *   [Prerequisites](#prerequisites)
    *   [Installation & Setup](#installation--setup)
*   [🤖 The AI Perception Core](#-the-ai-perception-core)
    *   [Why YOLOv11n + SCDepthV3?](#why-yolov11n--scdepthv3)
    *   [The Fusion Algorithm](#the-fusion-algorithm)
*   [🔮 Future Improvements](#-future-improvements)

### 💡 **The Idea: From Seeing to Understanding**

Standard cameras on heavy machinery are like eyes without a brain. They show an operator a 2D picture, but they don't provide the critical context needed for safety: *How far away is that person? Is that vehicle a potential collision risk?* This is reactive vision.

The core idea behind **LiteDepth** was to build an intelligent co-pilot that is **proactive**. Instead of just displaying a video feed, our system sees, understands, and communicates the 3D world in real-time. It learns what to look for, estimates the precise distance to any obstacle, and presents this complex information in an instantly understandable way.

This project implements that idea by building a sophisticated AI perception layer that runs entirely on a compact, low-power edge device, making it suitable for deployment on any machine.

### 💼 **Why This Project Matters: Solving Critical Safety Gaps**

On a busy industrial site, blind spots and misjudged distances can have catastrophic consequences. This project directly addresses key operational and safety problems:

*   **Eliminates Distance Ambiguity:** By providing real-world, metric distance to any detected object, the system removes the guesswork for operators, allowing for more confident and safer maneuvering.
*   **Reduces Cognitive Load:** The dual-display (AR + BEV) provides clear, glanceable alerts. An operator doesn't need to interpret a complex scene; they are immediately shown what matters, where it is, and if it's a threat.
*   **Prevents Accidents:** Proactive alerts for objects in critical safety zones give operators precious seconds to react, preventing potential collisions with personnel or other equipment.
*   **Demonstrates High-Performance Edge AI:** This project isn't just a cloud-based concept. It's a fully functional system that proves complex, multi-model AI pipelines can be deployed effectively on low-cost, power-efficient hardware, making advanced safety features accessible.

### 🚀 **Tech Stack & Architecture**

This system is built with a focus on performance, leveraging state-of-the-art open-source technologies.

| Technology | Role in Project |
| :--- | :--- |
| **Python** | 🐍 **The Core Logic:** The language used for the entire data pipeline, model integration, and visualization. |
| **PyTorch** | 🔥 **AI Framework:** The backbone for running both our object detection and depth estimation models. |
| **OpenCV** | 📸 **Computer Vision & Visualization:** The workhorse for video capture, image processing, and drawing all AR and BEV overlays. |
| **NumPy** | 🧮 **Numerical Operations:** Provides the high-performance array structures for handling images and depth maps efficiently. |
| **Raspberry Pi 5** | 🍓 **Edge Compute Platform:** The low-cost, powerful single-board computer that hosts our application. |
| **Hailo-8L AI Accelerator** | 🧠 **AI Inference Engine:** The specialized hardware that offloads all heavy neural network computations, enabling real-time performance. |
| **YOLOv11n** | 🎯 **Object Detection Model:** A highly efficient model, fine-tuned to identify worksite objects like people and vehicles. |
| **SCDepthV3** | 📏 **Depth Estimation Model:** A state-of-the-art model that generates a dense, metric depth map from a single 2D image. |

#### **Architecture Flowchart**

The data flows through the system in a high-speed, parallel loop:

 *(Note: Replace with an actual image of your Mermaid diagram)*

### ✨ **Key Features**

*   **Dual AI Pipeline:** Simultaneous object detection and depth estimation for maximum speed and efficiency.
*   **Real-Time Metric Ranging:** Calculates the precise distance in meters to any detected object.
*   **Augmented Reality (AR) Overlay:** Draws colored bounding boxes and attention lines directly onto the live video feed.
*   **Advanced Bird's-Eye View (BEV):** A dynamic, top-down tactical map with a pseudo-3D perspective grid, object motion trails, and blinking critical alerts.
*   **Consistent Visual Language:** A unified color-coding scheme (Red/Yellow/Green) is used across both AR and BEV displays for intuitive, zero-ambiguity threat assessment.
*   **Optimized for the Edge:** The entire system is engineered to run at **>30 FPS** on a low-power Raspberry Pi + Hailo hardware setup.

### 🖼️ **Visual Showcase: The LiteDepth System in Action**

The final output provides a comprehensive and intuitive understanding of the machine's surroundings.

*(Insert your best screenshots/GIFs here. For example:)*

| Live Combined View | AR View Detail | BEV Tactical Display |
| :---: | :---: | :---: |
|  |  |  |
| *The complete operator interface, showing the AR and BEV displays side-by-side.* | *Clear, colored bounding boxes provide immediate object identification and threat level.* | *The BEV shows object position, threat, motion history, and spatial context.* |

### 📂 **Project Structure**

The repository is organized logically to separate model files, core logic, and utility scripts.

```
LiteDepth-Caterpillar/
│
├── 📂 models/                # Contains the optimized model files (e.g., .onnx or other formats)
│   ├── yolov11n.onnx
│   └── scdepthv3.onnx
│
├── 📂 utils/                 # Utility scripts for things like calibration or color definitions
│   └── calibration.py
│
├── 📄 main.py                # The main application script that runs the entire pipeline
├── 📄 requirements.txt      # Python dependencies for the project
├── 📄 README.md              # You are here!
└── 📄 .gitignore             # Specifies files to ignore for Git
```

### 🏁 **Getting Started**

Follow these steps to get the LiteDepth system running.

#### **Prerequisites**

*   Python 3.8+
*   A clone of this repository
*   Hardware:
    *   Raspberry Pi 5
    *   Hailo-8L AI Accelerator (with drivers and SDK installed)
    *   A compatible camera (e.g., Raspberry Pi Camera Module)

#### **Installation & Setup**

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/your-username/LiteDepth-Caterpillar.git
    cd LiteDepth-Caterpillar
    ```

2.  **Set up a Virtual Environment (Recommended)**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Application**
    Ensure your camera is connected and the Hailo drivers are active.
    ```bash
    python main.py
    ```

### 🤖 **The AI Perception Core**

#### **Why YOLOv11n + SCDepthV3?**

This model pairing was a deliberate engineering choice to maximize performance on our edge device.

*   **YOLOv11n:** Chosen for its exceptional balance of speed and accuracy. The 'n' (nano) version is specifically designed for high-performance on resource-constrained devices, making it perfect for our >30 FPS target. We fine-tuned it on a custom dataset to improve its recognition of worksite-specific objects.
*   **SCDepthV3:** Selected for its state-of-the-art accuracy and, crucially, its ability to perform **zero-shot metric depth estimation**. This means it provides reliable distance measurements in meters on new, unseen environments without needing to be retrained, which is vital for a system deployed across diverse worksites.

#### **The Fusion Algorithm**

The "magic" of LiteDepth is how it combines the outputs of these two models in real-time.
1.  **Parallel Inference:** The system runs both models simultaneously to minimize latency.
2.  **High-Speed Lookup:** For every object YOLO detects, we take its representative point (the bottom-center for ground objects).
3.  **Direct Data Extraction:** We use the coordinates of this point to perform a direct, computationally cheap lookup into the NumPy array generated by SCDepthV3. This instantly gives us the object's distance. This method avoids any complex calculations and is key to maintaining our high frame rate.

### 🔮 **Future Improvements**

This project provides a robust foundation for a production-ready safety system. Here are some exciting next steps:

*   **🚨 Integrated Auditory Alerts:** Add sound cues that trigger when an object enters the critical "Red" zone, providing a non-visual alert for operators.
*   **🔄 Advanced Object Tracking:** Upgrade the basic motion trails to a more robust tracking algorithm like a Kalman Filter to predict object trajectories and provide early warnings for potential path intersections.
*   **🌍 360° Coverage:** Expand the system to use multiple cameras, fusing their outputs to create a seamless 360-degree BEV display that eliminates all blind spots around the vehicle.
*   **🌦️ All-Weather Performance:** Train the models on a dataset that includes nighttime, rain, and fog conditions, potentially using an IR camera feed, to ensure robust 24/7 operation.
