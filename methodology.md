# 🛠️ Methodology

This section details the models compared, the datasets or prompts used for generation, the experimental setup including hardware and software configurations, and the metrics employed for evaluation.

## Models Under Comparison
1.  **CausVid:**
    * Describe CausVid: e.g., "CausVid is a distilled version of the Wan 2.1 video generation model, optimized for faster inference and reduced computational load."
    * Source (if public, link to it, otherwise state its origin).
    * Key architectural features or differences from its parent model, if known.
2.  **[Model 2 Name - e.g., Wan 2.1 (Original)]:**
    * Description: [e.g., "The original Wan 2.1 model, serving as a baseline..."]
    * Source/Version.
    * Relevant architectural details.
3.  **[Model 3 Name - Optional, another comparative model]:**
    * Description.
    * Source/Version.
    * Relevant architectural details.
    * [Add more models as needed for your comparison.]

## Dataset and Prompts
* **Prompt Design:** Describe the nature of the text prompts used for text-to-video generation. Were they from a standard set, or custom-designed? Provide examples.
    * Example Prompts: ["A cat wearing a superhero cape flying through a cityscape", "Drone footage of a tropical beach at sunset", etc.]
* **Input Data (if applicable):** If using image-to-video or video-to-video, describe the source and nature of input images/videos.
* **Generation Consistency:** Detail how you ensured fair comparison (e.g., using the same set of prompts for all models).

## Experimental Setup
* **Hardware:**
    * **GPU:** NVIDIA H100 PCIe 80GB HBM3
    * **CPU:** [Specify CPU model, e.g., Intel Xeon Platinum XXXX]
    * **RAM:** [Specify system RAM, e.g., 512GB DDR5]
    * **Storage:** [Specify type, e.g., NVMe SSD]
* **Software:**
    * **Operating System:** [e.g., Ubuntu 22.04]
    * **CUDA Version:** [e.g., CUDA 12.x]
    * **cuDNN Version:** [e.g., cuDNN 8.x]
    * **NVIDIA Driver Version:** [e.g., 5XX.XX]
    * **Key Libraries:** [e.g., PyTorch (version), Diffusers (version), Transformers (version), ComfyUI (if used, specify version/setup), etc.]
    * Any other relevant software or environment details.
* **Generation Parameters (CausVid on H100):**
    * **Steps:** 6
    * **Classifier-Free Guidance (CFG) Scale:** 1
    * **Resolution:** 832x480 pixels
    * **Frame Count:** 81 frames per video
    * [Specify any other fixed parameters for CausVid: sampler used, seed (if fixed for reproducibility of specific examples, or range if varied)]
* **Generation Parameters (Other Models):**
    * Detail the parameters used for each of the other models being compared. Aim for settings that represent common usage or recommended settings for those models, or settings that allow for a fair comparison (e.g., similar output quality goals or frame counts if possible).

## Evaluation Metrics
### Quantitative Metrics
* **Peak VRAM Usage (GB):** Maximum GPU memory allocated during the generation process.
    * *Measurement for CausVid (H100): 21.56GB*
* **Generation Time (Prompt to Output, seconds per video):** Total wall-clock time from submitting the prompt (and any input data) to receiving the final video output file for a single, isolated generation.
    * *Measurement for CausVid (H100): 43 seconds per video*
* **Sampling Time (seconds per video):** Time taken specifically for the iterative denoising/sampling loop.
    * *Measurement for CausVid (H100): 21 seconds per video*
* **Iterations per Second (it/s):** Speed of the sampling loop.
    * *Measurement for CausVid (H100): 3.65 it/s (derived from 81 frames / (21s * [frames_per_step_if_relevant]) or 6 steps / 21s if 'it' refers to sampling steps. Clarify: 81 frames / 21s sampling time = ~3.85 frames/sec if 'it' refers to frames. Or if 6 steps over 21s, it's ~0.28 steps/sec. The 3.65 it/s needs context: is an "iteration" one sampling step, or generation of one frame? Given 6 steps, 21s sampling time for 81 frames, 3.65it/s for the steps would mean ~1.64s total for 6 steps, which is too fast. If "it" refers to frames, then 81 frames / 21s sampling = ~3.85 frames/s. The provided 3.65it/s for 21s sampling implies ~76 iterations. This could be 76 total sampling steps across the 81 frames, or perhaps an internal batching. Please clarify how "it/s" is defined in your context.*
* **Total Start-to-Finish Time (seconds):** This was mentioned as "37 seconds start to finish (22s per video)". Clarify if this 37s is for a single video including all overheads (model loading, etc. for a first run) or for a small batch where the average then becomes 22s.
    * *Measurement for CausVid (H100): 37 seconds (context dependent), 22 seconds per video (likely average in a sequence/batch)*
* **Video Quality Metrics (Optional but Recommended):**
    * Fréchet Video Distance (FVD)
    * Inception Score (IS) for videos
    * CLIP Score (for text-video alignment)
    * [Other relevant objective metrics]

### Qualitative Metrics
* **Visual Fidelity:** Sharpness, detail, realism, absence of blur.
* **Temporal Coherence:** Smoothness of motion, consistency of objects and scenes over time, absence of flickering or major inconsistencies between frames.
* **Prompt Adherence:** How well the generated video matches the input text prompt.
* **Artifacts:** Presence of visual glitches, distortions, or unnatural elements.
* **Assessment Method:** Describe how qualitative aspects were evaluated (e.g., rating by human evaluators, side-by-side comparisons, specific criteria checklist).

[Ensure all measurement methodologies are clear and reproducible.]