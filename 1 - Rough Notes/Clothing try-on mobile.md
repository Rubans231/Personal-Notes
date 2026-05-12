
2026-03-29 09:00

Status:

Tags: 




# Clothing try-on mobile

## 1. Project Objective
Deploy a real-time, fully offline, and prompt-less Virtual Try-On (VTON) pipeline natively on a mobile device constraint (Snapdragon 888, 8GB RAM / ~5GB usable). 

**Core Strategy:** Move all heavy compute, language encoding, and dataset generation to a dedicated Arch Linux desktop environment. Export highly distilled, purely vision-based ONNX models to the Android device, utilizing the Hexagon NPU and Adreno GPU to bypass CPU thermal throttling and Out of Memory (OOM) crashes.

---

## 2. The Core Architecture

### A. The Generative Model: Distilled CatVTON (Concatenation Concept)
* **Concept:** Eliminates the need for text encoders (CLIP) and IP-Adapters by stitching the inputs (masked person + target garment) into a single image collage (side-by-side or stacked 7-channel tensor).
* **Teacher Model:** Flux 9B (or high-quality IDM-VTON).
* **Student Model:** A custom, heavily distilled ~300M parameter UNet or DiT (Diffusion Transformer) trained purely on the concatenated collage format.

### B. The Masking Model: Target-Aware YOLO (Visual Prompting)
* **Concept:** Eliminates the need for cloud-based LLM orchestration or text prompts. The segmentation model dynamically masks the user based on the visual context of the target garment.
* **Teacher Model:** Grounded SAM 2 (Desktop).
* **Student Model:** YOLO11n-seg modified with a microscopic reference encoder (e.g., MobileNetV3) to accept a visual feature vector of the garment, dictating what to mask on the user.

---

## 3. The Execution Phases

### Phase 1: Dataset Generation (Arch Linux Desktop)
Automate the creation of a massive, flawless synthetic dataset to teach the mobile models.
1.  **Generate Masks:** Feed 50,000+ images into Grounded SAM 2 using text prompts (e.g., "segment the upper clothes") to extract pristine ground-truth silhouettes.
2.  **Generate Try-Ons:** Use the heavy Teacher model (Flux 9B/IDM-VTON) to generate the ground-truth final images of the person wearing the target garment.
3.  **Format Data:** Pre-process the dataset into the "collage" format: [Masked Person Image + Garment Image] -> [Ground Truth Dressed Person].

### Phase 2: Knowledge Distillation Training (Arch Linux Desktop)
Train the microscopic student models to replicate the Teacher's outputs.
1.  **Train Target-Aware YOLO:** Train the modified YOLO11n-seg to match Grounded SAM 2's masks, conditioned entirely on the visual feature vector of the reference garment.
2.  **Train Student CatVTON:** Train the ~300M parameter UNet to denoise the concatenated collage inputs into the ground-truth final images. Use MSE loss for structure and LPIPS (perceptual loss) to retain fabric textures.

### Phase 3: Mobile Export & Optimization
Convert the PyTorch `.pth` files into edge-compatible formats to run on mobile hardware accelerators.
1.  **Format:** Export both the Target-Aware YOLO and Student CatVTON to **ONNX** (or NCNN).
2.  **Quantization:** Apply **FP16** (16-bit float) quantization to halve the file sizes (YOLO to <15MB, CatVTON to ~600MB) without destroying structural integrity or triggering artifacting.

### Phase 4: Android Deployment (Native App)
Build the local orchestrator logic in Kotlin/Java.
1.  **Capture:** User takes a selfie and selects a target garment.
2.  **Visual Prompt (NPU):** Pass the garment image into the Target-Aware YOLO's reference encoder to extract its features.
3.  **Segment (NPU):** Pass the selfie and the garment features into YOLO to generate a precise mask (e.g., erasing only the shirt) in <50ms.
4.  **Stitch (CPU):** Use OpenCV to mathematically erase the old clothing using the mask, and concatenate the erased selfie with the garment image into a single tensor collage.
5.  **Generate (GPU/NPU):** Pass the unified collage into the Student CatVTON ONNX model.
6.  **Display:** Crop the output tensor to isolate the dressed person and render it on screen.



## NEW IDEAS

1. generate a quick bad photoshoped reference image of the clothing in the correct layer with the outfit on the person and then generate an actual real image with that as base
2. generate a quick on-the-fly reference sheet on the person wearing the clothing from different angle with character sheet lora
3. generate initial frame with reference sheet as context.
4. 3. with initial frame and current live video frame as reference, generate new frame through densepose, genAI and spatial reasoning
   
#### Additional

1. remove text parsing from the gen model.
2. concatenate input images

## Done so far

1. fought with gemini pro to make a initial dataset script to scrape vids off yt and use parts of it as separate data. we use gemma 4 E4B to identify cuts in the video and treat them as parts of the video
2. the idea is to generate vids with ltx 2.3 with the initial dataset and then use that data to train a whole model

# References