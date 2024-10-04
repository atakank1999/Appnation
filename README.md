# **Van Gogh Style Transfer**

https://openart.ai/workflows/dugong_active_88/appnation/ScVBMlaaieo3OriQWmBZ

This repository provides a workflow for generating images in the **Van Gogh style** using **ComfyUI**, **IPAdapter**, **Stable Diffusion**, and **ControlNet**. 

![Untitled design (1)](https://github.com/user-attachments/assets/a0c65694-5b59-4396-b0b6-dc9faa6c70e9)


## **Installation**

### **1. Clone the Repository**
First, clone the repository to your local machine:

```bash
git clone https://github.com/atakank1999/Appnation.git
```

### **2. Install Dependencies**
Make sure you have the following dependencies installed on your system:
- Python 3.8+
- ComfyUI
After installing ComfyUI, I used the following custom nodes from the manager:
- ComfyUI-Manager (https://github.com/ltdrdata/ComfyUI-Manager)
- ComfyUI's ControlNet Auxiliary Preprocessors (https://github.com/Fannovel16/comfyui_controlnet_aux)
- ComfyUI_IPAdapter_plus (https://github.com/cubiq/ComfyUI_IPAdapter_plus)
### **3. Download Required Models**

Some models are available to download from the ComfyUI Manager.
- Stable Diffusion Checkpoint: Juggernaut-XL-v9: https://huggingface.co/RunDiffusion/Juggernaut-XL-v9/blob/main/Juggernaut-XL_v9_RunDiffusionPhoto_v2.safetensors
- Depth anything: https://huggingface.co/spaces/LiheYoung/Depth-Anything/blob/main/checkpoints/depth_anything_vitl14.pth
- ControlNet:
  - t2i-adapter-lineart-sdxl-1.0:  https://huggingface.co/TencentARC/t2i-adapter-lineart-sdxl-1.0
  - control-lora depth and canny models https://huggingface.co/stabilityai/control-lora
  
### **4. Loading the Workflow**
Once ComfyUI is running, load the provided **Van Gogh style transfer workflow** by importing the JSON file included in this repository:
1. Open ComfyUI in your browser.
2. Go to the **"Load Workflow"** option.
3. Select the `appnation.json` file provided.

### **5. Setting Up Your Input**
- Upload the **input image**  via the **LoadImage** node at the bottom.

## **Common Problems**
The IPAdapterPlus custom node might provide a Clipvision Model Not Found error. To solve this issue, follow these instructions:
1. Download a clip vision model (https://huggingface.co/laion/CLIP-ViT-bigG-14-laion2B-39B-b160k) and move it to ComfyUI/models/clip_vision folder.
2. On the ComfyUI/custom_nodes/ComfyUI_IPAdapter_plus/utils.py line 17, make sure that the pattern matches the name of the clip vision model you downloaded previously
