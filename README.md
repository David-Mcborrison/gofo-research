# Comparative Study of CausVid Video Generation

This repository hosts the research paper and supplementary materials for a comparative study on CausVid video generation, including performance benchmarks on the NVIDIA H100 GPU.

**Navigate the Paper:**
* [Abstract (Home)](index.md)
* [Introduction](introduction.md)
* [Related Work](related_work.md)
* [Methodology](methodology.md)
* [Results](results.md)
* [Discussion](discussion.md)
* [Conclusion](conclusion.md)
* [References](references.md)
* [Appendix](appendix.md) (Optional)

## Quick Overview of H100 Performance (CausVid)
The following performance metrics were recorded for video generation using CausVid on an NVIDIA H100 80GB HBM3:
- **Parameters**: 6 Steps, 1 CFG
- **Resolution**: 832x480
- **Frame Count**: 81 frames
- **Total Time (Start to Finish for a process, e.g., a batch or single initial run)**: 37 seconds
- **Time Per Video (likely in continuous/batched generation)**: 22 seconds
- **Peak VRAM Usage**: 21.56GB
- **Generation Time (Prompt to Output for an isolated video)**: 43 seconds per video
- **Sampling Time (Core generation loop)**: 21 seconds per video (3.65 it/s)

For full details, please see the [Methodology](methodology.md) and [Results](results.md) sections.