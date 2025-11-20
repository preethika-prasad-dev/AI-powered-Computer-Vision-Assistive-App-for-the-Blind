<div align="center">

# ✨ AI-Powered Computer Vision Assistive App for the Blind ✨  
### Built by **Preethika Prasad**

*A real-time intelligent camera assistant that empowers visually impaired users through audio-based scene understanding.*

</div>

---

## 📋 Overview

The **AI-Powered Computer Vision Assistive App for the Blind** is a camera-based assistive solution designed to help visually impaired users understand their surroundings through **real-time audio descriptions**.

This system integrates:

- **Object Detection (OpenCV)**
- **Text Recognition (Tesseract OCR)**
- **Face Recognition (CNN)**
- **Text-to-Speech (TTS)**

…to provide fast, reliable, and accessible auditory feedback without requiring any visual interaction.

---

## 🧠 Core Functionalities

### 👁️ Real-Time Object Detection  
- Detects everyday objects using OpenCV  
- Announces object name + spatial position (left, right, center)

### 📝 OCR Text Reading  
- Reads printed and handwritten text from signs, labels, menus, documents  
- Converts extracted text into clear spoken output

### 🙂 Face Recognition  
- CNN-based face recognition  
- Identifies familiar individuals (optional training)

### 🔊 Audio Feedback (TTS)  
- Natural-sounding speech output  
- Designed for blind-first interaction  
- No need to touch the screen or navigate menus

---

## 🏗️ System Architecture

```mermaid
graph TD
    User([User]) --> |Camera Input| Camera[Camera Frame Capture]

    Camera --> Router{Scene Type Detector}

    Router -->|Object| ObjDetect[Object Detection (OpenCV)]
    Router -->|Text| Ocr[Tesseract OCR]
    Router -->|Face| FaceRec[CNN-based Face Recognition]

    ObjDetect --> Processor[Result Processing]
    Ocr --> Processor
    FaceRec --> Processor

    Processor --> TTS[Text-to-Speech Engine]
    TTS --> Output["Audio Output to User"]
    
    classDef input fill:#e6f7ff,stroke:#1890ff,stroke-width:2px
    classDef process fill:#f6ffed,stroke:#52c41a,stroke-width:1px
    classDef decision fill:#fff7e6,stroke:#fa8c16,stroke-width:1px
    classDef output fill:#f9f0ff,stroke:#722ed1,stroke-width:1px

    class User input
    class Camera,ObjDetect,Ocr,FaceRec,Processor,TTS process
    class Router decision
    class Output output
