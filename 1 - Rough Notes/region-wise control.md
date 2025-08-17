
2025-08-17 14:55

Status:

Tags: [[LLMs(Large language models)]] [[algorithm]] [[videogeneration]] 




# region-wise control

- Modern approaches typically regard the condition of Gaussian filtered point-wise trajectory as sole motion control signal. This severely limits the controllable capacity of fine-grained movement, and commonly fails to disentangle object and camera moving
- region-wise motion controller that leverages precise region-wise trajectory and motion mask to regulate fine-grained motion synthesis and identify exact target motion category (i.e., object or camera moving), respectively.
- ReMoCo first estimates the flow maps on each training video via a tracking model, and then samples the region-wise trajectories from multiple local regions to simulate inference scenario. Instead of approximating flow distribution via Gaussian filtering, our region-wise trajectory preserves original flow information at local area and thus manages to characterize fine-grained movement.
- A motion mask is simultaneously derived from the predicted flow maps to present holistic motion dynamics. To pursue natural and controllable motion generation, ReMoCo further strengthens video denoising with additional conditions of region-wise trajectory and motion mask in a feature modulation manner.
- the developers of this model meticulously construct a benchmark called ReMoCo-Bench, which consists of 1.1K real-world user-annotated image-trajectory pairs, for the evaluation of both fine-grained and object-level motion synthesis in I2V generation. Extensive experiments conducted on WebVid-10M and ReMoCo-Bench demonstrate the effectiveness of our ReMoCo for precise motion control.
- Used in [[Tooncomposer]] 




# References