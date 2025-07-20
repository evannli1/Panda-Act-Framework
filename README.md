# Panda Act: A Framework for Robotic Manipulation Tasks Based on Multiple Zero-Shot Models

## Overview

**Panda Act** is a novel robotic manipulation framework that leverages large language models (LLMs) and multimodal zero-shot models to enable robots to execute complex manipulation tasks without requiring additional training. The framework integrates linguistic, visual, and auditory zero-shot models through a multi-layer modular architecture.

### Key Features

- **Zero-shot Learning**: Execute unknown tasks without task-specific training
- **Multimodal Interaction**: Support for language, image, and audio instructions
- **Modular Architecture**: Four-layer design with interchangeable components
- **Real-world Validation**: Tested in both simulation (PyBullet) and real environments (Dobot arm)

## Architecture

The framework consists of four functional layers:

1. **Task Instruction Understanding Layer**: Processes natural language and multimodal instructions using LLMs
2. **Visual Image Segmentation Layer**: Segments environmental images using SAM-based models
3. **Cross Modal Matching Layer**: Matches task features with environmental features
4. **Robotic Action Control Layer**: Executes robot actions based on target identification

### Integrated Models

#### Language Models
- GPT-4 (OpenAI)
- Text-Davinci-003 (OpenAI)
- Llama3 (Meta)

#### Visual Segmentation Models
- SAM (Segment Anything Model)
- HQ-SAM (High-Quality SAM)
- Mobile-SAM (Efficient SAM)

#### Cross-Modal Matching Models
- CLIP (OpenAI)
- Open-CLIP
- ImageBind (Meta)

## Interaction Modes

### 1. Pure-Language Interaction
Execute tasks based on natural language descriptions:
```
"Put the greens on the plate"
"Hurry up and put the apples in the fruit basket"
```

### 2. Language-Image Interaction
Use reference images to specify target objects:
```
"Place the object in image1 on image2"
```

### 3. Language-Sound Interaction
Locate objects based on environmental sounds:
```
"Put the ringing alarm clock on a plate"
"Rotate the ringing alarm clock by 90 degrees"
```

### 4. Directed-Enhanced Interaction
Interactive GUI for object selection when verbal description is insufficient:
```
"I don't know how to describe this object"
```

## Installation

### Prerequisites
- Python 3.8+
- PyTorch 1.9+
- OpenCV 4.5+
- PyBullet (for simulation)
- Intel RealSense SDK (for real robot)

### Dependencies
```bash
pip install -r requirements.txt
```

## Framework Design Overview

The Panda Act framework implements a four-layer architecture:

```
┌─────────────────────────────────────────────────────────────┐
│ Task Instruction Understanding Layer (LLM Processing)        │
│ • GPT-4, Text-Davinci-003, Llama3                          │
├─────────────────────────────────────────────────────────────┤
│ Visual Image Segmentation Layer                             │
│ • SAM, Mobile-SAM, HQ-SAM                                  │
├─────────────────────────────────────────────────────────────┤
│ Cross Modal Matching Layer                                  │
│ • CLIP, Open-CLIP, ImageBind                              │
├─────────────────────────────────────────────────────────────┤
│ Robotic Action Control Layer                               │
│ • Pick & Place, Rotation, Push Actions                    │
└─────────────────────────────────────────────────────────────┘
```


## Hardware Requirements

### Simulation
- CPU: Intel i5 or equivalent
- RAM: 8GB minimum, 16GB recommended
- GPU: NVIDIA GTX 1060 or better (for zero-shot models)

### Real Robot Setup
- Dobot Magician robotic arm
- Intel RealSense D435i depth camera
- Microphone for audio input (language-sound interaction)
- Workstation with GPU support


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

We thank the developers of the foundational models used in this framework:
- OpenAI for GPT-4 and CLIP
- Meta for SAM, ImageBind, and Llama3
---

The complete framework implementation will be released soon.