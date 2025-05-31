# 📚 Related Work

This section reviews prior research pertinent to our study, focusing on advancements in AI video generation, model distillation techniques for efficiency, and existing comparative benchmarks.

## AI Video Generation Models
Discuss prominent architectures and approaches:
* **Diffusion Models in Video:** Detail the rise of diffusion models for image and video synthesis. Mention foundational papers and models that paved the way (e.g., DDPMs, Latent Diffusion Models). Specifically discuss models relevant to your comparison, such as the original Wan 2.1 (if CausVid is derived from it) and other leading open or closed-source video generation models ([e.g., Stable Video Diffusion, Imagen Video, Make-A-Video, Pika, Runway Gen-2, etc.]). Highlight their strengths and typical computational costs if known.
* **GAN-based Video Generation:** Briefly touch upon earlier generative adversarial network approaches for video (e.g., [mention key GAN models for video like MoCoGAN, TGAN, etc.]) and their limitations compared to recent diffusion models.
* **Autoregressive Models / Transformers for Video:** Mention any significant contributions using transformer architectures directly for video pixel modeling (e.g., [VideoGPT, Phenaki, etc.]), noting their approach to temporal dynamics.
* **Other Relevant Architectures:** [Include any other categories of models relevant to your specific comparison or the techniques used in CausVid].

## Model Distillation and Optimization for Generative Models
Review techniques used to make large generative models more efficient, with a focus on those applicable to video models:
* **Knowledge Distillation:** Explain the general principle. Discuss any known applications of knowledge distillation to large image or video diffusion models. If CausVid is a result of distillation, this section is crucial. Cite relevant papers on distillation methodologies (e.g., response-based, feature-based, relation-based).
* **Quantization and Pruning:** Briefly discuss how these techniques reduce model size and potentially speed up inference, and whether they are commonly applied to the types of models you are studying.
* **Architectural Optimizations:** Mention efforts in creating more efficient architectures from the ground up, or specific optimizations applied to transformer or U-Net backbones common in diffusion models.
* **Efficient Sampling Methods:** Discuss samplers for diffusion models (e.g., DDIM, DPM-Solver, PLMS) and how they can reduce the number of steps required for generation, which is a key factor in speed. Note the "6 Steps" parameter you've used for CausVid.

## Comparative Studies and Benchmarks
* Survey any existing comparative studies of video generation models.
* Discuss common benchmarks or datasets used for evaluating video generation quality (e.g., UCF101, Kinetics, MSR-VTT for content; FVD, IS, FID for perceptual quality).
* Position your work: Explain how your study, particularly with its focus on CausVid and H100 performance, adds to or differs from existing literature. Highlight the novelty of benchmarking a distilled model like CausVid on this specific high-end hardware.

[Ensure to cite all sources properly. These will go into your `references.md` file.]