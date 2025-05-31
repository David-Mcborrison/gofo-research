# 📊 Results

This section presents the findings from our comparative experiments, focusing on the performance and output characteristics of CausVid and the other models evaluated.

## Performance Benchmarks

### CausVid on NVIDIA H100
The performance of CausVid was specifically benchmarked on an NVIDIA H100 80GB HBM3 GPU with the following parameters: 6 Steps, 1 CFG, 832x480 resolution, 81 frames.

* **Peak VRAM Usage:** **21.56 GB**
* **Generation Time (Prompt to Output):** **43 seconds per video**
    * This metric represents the total wall-clock time for generating a single video from prompt submission to file output in an isolated run.
* **Sampling Time:** **21 seconds per video**
    * This is the core time spent in the iterative generation (denoising/sampling) loop.
* **Sampling Speed:** **3.65 it/s**
    * [Provide clarification here based on your definition of "iteration" as noted in Methodology. E.g., "This corresponds to X frames per second processed during the sampling phase" or "Y sampling steps completed per second."]
* **Overall Throughput (Start-to-Finish):**
    * A representative generation process completed in **37 seconds start to finish.**
    * In continuous or batched generation scenarios, the effective time per video was approximately **22 seconds.**
    * [Elaborate on the context of these two figures, e.g., "The 37-second figure includes initial setup/model loading for a session, while the 22-second figure reflects the amortized time per video when generating multiple videos consecutively."]

*(Table 1: Summary of CausVid Performance on NVIDIA H100)*
| Metric                        | Value          | Notes                                             |
|-------------------------------|----------------|---------------------------------------------------|
| GPU                           | NVIDIA H100    | 80GB HBM3                                         |
| Steps                         | 6              |                                                   |
| CFG Scale                     | 1              |                                                   |
| Resolution                    | 832x480        |                                                   |
| Frame Count                   | 81             |                                                   |
| Peak VRAM Usage               | 21.56 GB       |                                                   |
| Generation Time (Prompt-Output) | 43s / video    | Isolated run                                      |
| Sampling Time                 | 21s / video    | Core generation loop                              |
| Sampling Speed (it/s)         | 3.65 it/s      | [Clarify definition of 'it']                      |
| Start-to-Finish (Total)       | 37s            | [e.g., Single video with overhead / batch init]   |
| Avg. Time per Video (Batch)   | ~22s / video   | [e.g., Amortized in continuous generation]        |


### Comparative Performance
Present tables and charts comparing CausVid against [Model 2], [Model 3], etc., across the quantitative metrics defined in the Methodology.

*(Table 2: Comparative Generation Times and VRAM Usage)*
| Model     | Avg. Gen Time (s/video) | Peak VRAM (GB) | Sampling Time (s/video) | Output Resolution | Key Parameters |
|-----------|-------------------------|----------------|-------------------------|-------------------|----------------|
| CausVid   | 43 (or 22, be consistent) | 21.56          | 21                      | 832x480           | 6 steps, 1 CFG |
| [Model 2] | [Your Value]            | [Your Value]   | [Your Value]            | [Your Value]      | [Your Value]   |
| [Model 3] | [Your Value]            | [Your Value]   | [Your Value]            | [Your Value]      | [Your Value]   |
| ...       | ...                     | ...            | ...                     | ...               | ...            |

[Include charts here if useful, e.g., bar charts for speed comparison, VRAM usage. You can create these as images and place them in the `assets/images/` folder, then link them: `![Chart Title](assets/images/chart_name.png)`]

## Qualitative Results

Describe the observed qualitative differences.
* **Visual Fidelity and Artifacts:**
    * CausVid: [Describe observations. E.g., "CausVid produced videos with generally good detail for its speed, though occasional minor artifacts such as [specific examples] were observed at 6 steps..."]
    * [Model 2]: [Describe observations]
    * [Model 3]: [Describe observations]
* **Temporal Coherence:**
    * CausVid: [Describe observations. E.g., "Motion was largely smooth, but complex object interactions sometimes showed minor inconsistencies..."]
    * [Model 2]: [Describe observations]
    * [Model 3]: [Describe observations]
* **Prompt Adherence:**
    * CausVid: [Describe observations. E.g., "The model generally adhered well to simple prompts. For more complex prompts involving multiple interacting elements..."]
    * [Model 2]: [Describe observations]
    * [Model 3]: [Describe observations]

### Example Generations
Provide visual examples. You can use stills (images) for keyframes or embed short GIFs/videos if your hosting setup supports it well (consider Git LFS for video files).

**Prompt: "A majestic robot eagle soaring over a futuristic city at dawn"**

**CausVid (832x480, 81f, 6 steps):**
`![CausVid Example 1 Still](assets/images/causvid_ex1_still.jpg)`
*(Link to video: `[Video Link](assets/videos/causvid_ex1.mp4)`)*

**[Model 2 Name]:**
`![Model 2 Example 1 Still](assets/images/model2_ex1_still.jpg)`
*(Link to video: `[Video Link](assets/videos/model2_ex1.mp4)`)*

[Repeat for a few diverse prompts to showcase strengths and weaknesses.]