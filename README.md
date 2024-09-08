# When AI Eats Itself: On the Caveats of AI Autophagy in the Era of Generative AI

![Awesome](https://awesome.re/badge.svg)

A curated list of research papers on Generative AI Autophagy, a phenomenon where AI models are trained on synthetic data instead of real data, based on our paper "When AI Eats Itself: On the Caveats of AI Autophagy in the Era of Generative AI." The term "Autophagy" is attributed to the paper "Self-Consuming Generative Models Go MAD".

## 📑 Table of Contents

- [Introduction](#introduction)
- [What are the consequences of out-of-control autophagy with synthetic content?](#what-are-the-consequences-of-out-of-control-autophagy-with-synthetic-content)
  - [Theoretical Intuition](#theoretical-intuition)
  - [Impact of AI Autophagy on Vision Models](#impact-of-ai-autophagy-on-vision-models-quality-degradation-mode-collapse)
  - [Impact of AI Autophagy on Language Models](#impact-of-ai-autophagy-on-language-models-mode-collapse-break-of-scaling-laws)
- [What technical strategies can mitigate the negative consequences of AI autophagy?](#what-technical-strategies-can-mitigate-the-negative-consequences-of-ai-autophagy)
  - [🍒 "Cherry-picking": Filter out low quality synthetic data during training](#🍒-cherry-picking-filter-out-low-quality-synthetic-data-during-training)
  - [💧 Watermarking: Mark synthetic data (and filter them out during training)](#💧-watermarking-mark-synthetic-data-and-filter-them-out-during-training)
  - [🔍 Detection: Identify synthetic data (and filter them out during training)](#🔍-detection-identify-synthetic-data-and-filter-them-out-during-training)
- [What regulatory strategies can address these negative consequences?](#what-regulatory-strategies-can-address-these-negative-consequences)
- [Contributing](#contributing)
- [License](#license)

##  Introduction

Deep learning-based generative models have significantly transformed AI and machine learning. These models generate realistic data for images, text, speech, and music, with innovations like **DALL-E 2**, **Imagen**, **Suno**, and **Sora**, alongside advanced language models like **ChatGPT**. These technologies enable seamless integration of visual, textual, and auditory data.

Training these models requires extensive, high-quality datasets, often sourced from web scraping. For instance, **CommonCrawl** is a widely used petabyte-scale open-source web crawling database. However, as web scraping increases, so does the risk of incorporating synthetic data generated by other models, leading to potential performance degradation. This phenomenon, termed **"autophagy,"** occurs when models are trained on AI-generated content, potentially causing models to consume themselves.

While synthetic data can initially seem beneficial, over-reliance can lead to negative impacts such as performance degradation and diversity drop. There is a significant gap in the literature on the comprehensive impact of synthetic data use across different modalities.

![AI Autophagy Loop](https://github.com/user-attachments/assets/af1bc857-0dbf-41fd-93c1-65523c3eb1da)

##  What are the consequences of out-of-control autophagy with synthetic content?

###  Theoretical Intuition

| Title | arXiv | Pub. & Date | Theoretical Model |
|-----|-----|-----|-----|
| [Model Collapse Demystified: The Case of Regression](https://arxiv.org/abs/2402.07712) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2402.07712) | Feb. 2024 | Gaussian and ridge regression |
| [On the Stability of Iterative Retraining of Generative Models on their own Data](https://arxiv.org/abs/2310.00429) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2310.00429) | Sep. 2023 | Multi-variate Gaussian |
| [Self-Consuming Generative Models Go MAD](https://arxiv.org/abs/2307.01850) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2307.01850) | Jul. 2023 | Single dimensional Gaussian  |
| [The Curse of Recursion: Training on Generated Data Makes Models Forget](https://arxiv.org/abs/2305.17493) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.17493) | May 2023 | Single dimensional Gaussian |


### Impact of AI Autophagy on Vision Models (Quality Degradation, Mode Collapse)

| Title | arXiv | Pub. & Date | Key Findings |
|-----|-----|-----|-----|
| [Self-Consuming Generative Models Go MAD](https://arxiv.org/abs/2307.01850) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2307.01850) | Jul. 2023 | "Cherry-picking" during the autophagy loop (only using good-looking data for downstream tasks) exaggerates mode collapse in further iterations. Access to human-generated content mitigates quality degradation. |
| [Combining Generative Artificial Intelligence (AI) and the Internet](https://arxiv.org/abs/2303.01255) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2303.01255) | Feb. 2023 | Noted fuzziness and information loss in images during AI autophagy. |
| [Towards Understanding the Interplay of Generative Artificial Intelligence and the Internet](https://arxiv.org/abs/2306.06130) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2306.06130) | Jun. 2023 | AI autophagy can lead to degeneration and loss of diversity. |
| [Nepotistically Trained Generative-AI Models Collapse](https://arxiv.org/abs/2311.12202) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2311.12202) | Nov. 2023 | Even when retrained on even small amounts of their own creation, powerful StableDiffusion produce highly distorted images. |



### Impact of AI Autophagy on Language Models (Mode Collapse, Break of Scaling Laws)
| Title | arXiv | Pub. & Date | Key Findings |
|-----|-----|-----|-----|
| [The Curse of Recursion: Training on Generated Data Makes Models Forget](https://arxiv.org/abs/2305.17493) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.17493) | May 2023 | Autophagy fine-tuning leads to repetitive phrases (mode collapse); access to human-generated content is essential. |
| [A Tale of Tails: Model Collapse as a Change of Scaling Laws](https://arxiv.org/abs/2402.07043) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2402.07043) | Feb. 2024 | Synthetic data disrupts scaling laws. |
| [The curious decline of linguistic diversity: Training language models on synthetic text](https://arxiv.org/abs/2311.09807) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2311.09807) | Nov. 2023 | A consistent decrease in the diversity of the model outputs through successive iterations. |

##  What technical strategies can mitigate the negative consequences of AI autophagy?

### 🍒 "Cherry-picking": Filter out low quality synthetic data during training
**Personal Note**: Although some papers demonstrate the efficacy of cherry-picking in fine-tuning large language models, imaging data still suffers from a [quality-variety tradeoff](https://arxiv.org/abs/2307.01850).

| Title | arXiv | Pub. & Date | Key Findings |
|-----|-----|-----|-----|
| [Beyond Model Collapse: Scaling Up with Synthesized Data Requires Reinforcement](https://arxiv.org/abs/2406.07515) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2406.07515) | Jun. 2024 | Training from feedback-augmented synthesized data, either by pruning incorrect predictions or by selecting the best of several guesses, can prevent model collapse, validating popular approaches like RLHF. |
| [Self-Correcting Self-Consuming Loops for Generative Model Training](https://arxiv.org/abs/2402.07087) | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2402.07087) | Feb. 2024 | By introducing an idealized correction function, which maps a data point to be more likely under the true data distribution, self-consuming loops can be made exponentially more stable. |


### 💧 Watermarking: Mark synthetic data (and filter them out during training)
#### 📷 Image Watermarking
Watermarking synthetic images is a promising approach, already finding real-world applications in AI-driven image generation.

In 2023, Google DeepMind, in collaboration with Google Cloud, launched [SynthID](https://deepmind.google/technologies/synthid/), a beta tool for watermarking and identifying AI-generated images. SynthID subtly embeds a digital watermark within an image's pixels, making it invisible to the human eye but detectable for verification purposes. It was initially released to a select group of Vertex AI customers using Imagen, which is a text-to-image model producing photorealistic images. But the technical details of SynthID is not revealed. Similarly, StableDiffusion includes a feature in its [reference sampling script](https://github.com/CompVis/stable-diffusion#reference-sampling-script) which incorporates an invisible watermarking of the outputs using a Python Package invisible-watermark, to help viewers identify the images as AI-generated. The default setting in StableDiffusion inference used a combination of DCT and DWT algorithm. 

However, using watermarking for security or verification assumes uniform adoption of the same watermarking scheme across all image generators, which, while technically feasible, could be costive and prone to attacks. Moreover, an effective watermark detector (decoder) requires knowledge of the technical specifics of the watermarking technology. However, this is often not feasible as many companies are reluctant to disclose their proprietary technical details, posing a challenge to the widespread implementation and effectiveness of such watermarking systems.


| **Domain**              | **Technique**                               | **Description**                                                                                                               | 
|-------------------------:|---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| **Spatial Domain**      | Least Significant Bit (LSB)                 | Modifies the least significant bits of pixel values to embed the watermark.                                                   |  
|                         | Improvements to LSB                         | Includes techniques like [random embedding](https://ieeexplore.ieee.org/abstract/document/4656530?casa_token=3f4xpWiamTMAAAAA:26DU2v9tpFnN5Snaf7xGKhneD7infvSnBU6GGwBjiVvRc0KKI4EpNbSagxne4HKEkdEWmg) and [statistical similarity](https://ieeexplore.ieee.org/abstract/document/5955442?casa_token=p3vrruhM-YYAAAAA:5Lkv3YLwN_8XEtjsrn2d79qNDSLAHe2PyfyOKb-SMRb_tHFWCLgljYGpno8LZi3TYHX4nw) measures to enhance robustness and imperceptibility.     | 
| **Transform Domain**    | [Discrete Cosine Transformation (DCT)](https://www.sciencedirect.com/science/article/abs/pii/S0165168498000152)        | Transforms the image and embeds the watermark into selected spectral coefficients.                                            |
|                         | [Discrete Wavelet Transformation (DWT)](https://ieeexplore.ieee.org/document/918570)      | Uses wavelet transformation and pixel-wise masking for watermark embedding.                                                   |
|                         | [Discrete Fourier Transformation (DFT)](https://link.springer.com/chapter/10.1007/978-3-319-33618-3_36)       | Embeds watermark in the magnitude matrix of the DFT of the image.                                                             | 
| **Deep Watermarking**   | Deep Learning                               | [Convolutional Neural Networks (CNNs)](https://papers.nips.cc/paper_files/paper/2017/hash/838e8afb1ca34354ac209f53d90c3a43-Abstract.html), [attention-based networks](https://arxiv.org/abs/1909.01285), and [Long Short-Term Memory (LSTM) networks](https://arxiv.org/abs/1711.01306)  |

#### 📖 Text Watermarking

Similarly, as image watermarking techniques, watermarking may not effectively prevent the misuse of NLP generative models unless it is uniformly applied across all powerful LLMs. In real-world settings, where users typically have access only to black-box language models, it is impractical to manipulate the model’s vocabulary distribution or intervene in the text generation process. This limitation reduces the effectiveness of during LLM watermarking strategies. However, post LLM watermarking methods [fall short compared to integrated approaches in preserving the quality of generated texts](https://arxiv.org/abs/2307.15992), and they are [more susceptible to being circumvented by paraphrase attacks](https://arxiv.org/abs/2303.11156). 

| **Type of Watermarking** | **Paper Name**                         | **Link**                               | **Comments**                                                                                      | **Year** |
|--------------------------|----------------------------------------|----------------------------------------|---------------------------------------------------------------------------------------------------|----------|
| **Post LLM Watermarking** | Zero-Width Characters                 | N/A                                    | Involves inserting invisible Unicode characters, such as zero-width spaces, for encoding information. | N/A      |
|                          | Natural language processing for information assurance and security: an overview and implementations                | [🔗](https://dl.acm.org/doi/abs/10.1145/366173.366190?casa_token=qrsrM8ulhn4AAAAA:TjX1qmnc-msVn1G7DaSuNcDVo93SBjEKLidXsOvRtsy1I95KRncSx3D-PXWgLGg6RHGCc7z18Q) | Utilizes predefined rules and dictionaries for word replacement.                                  | 2001     |
|                          | Natural language watermarking: challenges in building a practical system      | [🔗](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/6072/60720A/Natural-language-watermarking-challenges-in-building-a-practical-system/10.1117/12.643560.short#_=_) | Modifies sentence structures using predefined rules.                                              | 2006     |
|                          | Adversarial Watermarking Transformer: Towards Tracing Text Provenance with Data Hiding        | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2009.03015) | Utilizes transformers for word modifications, may cause grammatical errors.                       | 2021     |
|                          | Robust Multi-bit Natural Language Watermarking through Invariant Features                        | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.01904) | Focuses on invariant features for word replacement.                                               | 2023     |
|                          | Watermarking Text Generated by Black-Box Language Models                 | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.08883) | Binary pattern alteration through word substitution.                                              | 2023     |
| **During LLM Watermarking** | A watermark for large language models                   | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2301.10226) | Encourages usage of specific words (green list) and prohibits others (red list).                   | 2023     |
|                          | Who Wrote this Code? Watermarking for Code Generation                 | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.15060) | Applies watermarking rules to tokens with certain entropy, optimizing for uniqueness.             | 2023     |


### 🔍 Detection: Identify synthetic data (and filter them out during training)
#### 📷 Synthetic Image Detection
Non-watermarking-based detection methods ensure there is no compromise in image quality. However, despite the wide proposal of methods claiming to be generalizable, it remains uncertain whether these detectors can be effectively applied to previously unseen synthetic images without thorough experimentation. 

| **Type of Detection**       | **Paper Name**                                        | **Link**                                                                 | **Comments**                                                                                      | **Year** |
|-----------------------------|-------------------------------------------------------|--------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------|
| **Deepfake Detection**      | Face X-ray for More General Face Forgery Detection    | [🔗](https://openaccess.thecvf.com/content_CVPR_2020/html/Li_Face_X-Ray_for_More_General_Face_Forgery_Detection_CVPR_2020_paper.html) |                      | 2020     |
|                             | The Creation and Detection of Deepfakes: A Survey     | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2004.11138)                         |                                          | 2021     |
|                             | Deepfake Generation and Detection: A Survey           | [🔗](https://link.springer.com/article/10.1007/s11042-022-12179-1)   |              | 2022     |
|                             | Deepfake Detection: A Systematic Literature Review    | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2403.17881)                   |                             | 2024     |
| **End-to-end Detection**    | CNN-Generated Images are Surprisingly Easy to Spot... | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/1912.11035) | A standard image classifier trained on only one specific CNN generator (Pro-GAN) is able to generalize surprisingly well to unseen architectures, datasets, and training methods.                                             | 2019     |
|                             | Fusing Global and Local Features for Generalized AI-Synthesized Image Detection | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2203.13964)                   |                              | 2022     |
|                             | Detecting GAN-Generated Images by Orthogonal Training of Multiple CNNs | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2203.02246)                   | Uses an ensemble strategy.                          | 2022     |
| **Fingerprints Extraction** | Detecting GAN-Generated Imagery Using Color Cues      | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/1812.08247)                               |                                               | 2018     |
|                             | Detecting GAN-Generated Imagery Using Saturation Cues | [🔗](https://ieeexplore.ieee.org/document/8803661)                   |                                  | 2019     |
|                             | Detecting GAN Generated Fake Images Using Co-occurrence Matrices | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/1903.06836)                               |                                           | 2019     |
|                             | Global Texture Enhancement for Fake Face Detection in the Wild | [🔗](https://openaccess.thecvf.com/content_CVPR_2020/html/Liu_Global_Texture_Enhancement_for_Fake_Face_Detection_in_the_Wild_CVPR_2020_paper.html) |                                      | 2020     |
|                             | Learning on Gradients: Generalized Artifacts Representation for GAN-Generated Images Detection | [🔗](https://openaccess.thecvf.com/content/CVPR2023/html/Tan_Learning_on_Gradients_Generalized_Artifacts_Representation_for_GAN-Generated_Images_Detection_CVPR_2023_paper.html) |                             | 2023     |
|                             | Detecting Generated Images by Real Images             | [🔗](https://link.springer.com/chapter/10.1007/978-3-031-19781-9_6)  | Image noise patterns                                          | 2022     |
|                             | Rich and Poor Texture Contrast: A Simple Yet Effective Approach for AI-Generated Image Detection |  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2311.12397)                               | Inter-pixel correlation within rich and poor texture regions                                         | 2023     |
|                             | Leveraging Frequency Analysis for Deep Fake Image Recognition |  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2003.08685)               |   Synthetic images have higher high-frequency components  compared to real ones.                                        | 2020     |
|                             | Watch Your Up-Convolution: CNN Based Generative Deep Neural Networks Are Failing to Reproduce Spectral Distributions | [🔗](https://openaccess.thecvf.com/content_CVPR_2020/html/Durall_Watch_Your_Up-Convolution_CNN_Based_Generative_Deep_Neural_Networks_Are_Failing_CVPR_2020_paper.html) | Spectral peaks that result from the upsampling processes commonly utilized in numerous GAN architectures.                         | 2020     |
|                             | Detecting and Simulating Artifacts in GAN Fake Images | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/1907.06515)                   |                                       | 2019     |
| **Diffusion Model Detection**| Towards the Detection of Diffusion Model Deepfakes    | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2210.14571)                               |                                    | 2022     |
|                             | On the Detection of Synthetic Images Generated by Diffusion Models | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2211.00680)                  |                   | 2022     |
|                             | DIRE for Diffusion-Generated Image Detection          | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2303.09295)                               | Introduces Diffusion Reconstruction Error (DIRE) for detecting images from diffusion models.       | 2023     |

#### 📖 Synthetic Text Detection
As the most widely adopted approach, non-watermark based detection techniques are prevalent across commercial platforms. A key advantage of these techniques over watermarking is their non-intrusive nature; they do not compromise text quality. Thus, we see a lot of detect algorithms based on non-watermarking techniques, such as [GPTZero](https://gptzero.me/),  [Originality.ai](https://originality.ai/), [Turnitin’s AI detection tools](https://www.turnitin.com/solutions/topics/ai-writing/). 

However, a significant challenge for non-watermark based LLM detectors lies in their generalizability, or their capacity to recognize AI-generated texts from new domains or models. Despite many algorithms boasting detection accuracies above 90% in their experimental result section, the boundary between human and AI-generated texts is becoming increasingly blurred as AI technology advances. For example, in the evaluations on a “challenge set” of English texts,[ OpenAI’s text classifier only identifies 26% of generated text](https://openai.com/index/new-ai-classifier-for-indicating-ai-written-text/). 

In addition, the [explainability](https://www.vanderbilt.edu/brightspace/2023/08/16/guidance-on-ai-detection-and-why-were-disabling-turnitins-ai-detector/) and [potential bias](https://arxiv.org/abs/2304.02819) of these detectors raise additional concerns, for which there are currently no definitive solutions. 

| **Type of Detection**             | **Paper Name**                                                    | **Link**                                                                             | **Comments**                                                                                      | **Year** |
|-----------------------------------|-------------------------------------------------------------------|--------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------|
| **End-to-End Detection**          | OpenAI Detection Tool                                             | [🔗](https://openai.com/blog/new-ai-classifier-for-indicating-ai-written-text)       | Uses a fine-tuned language model to distinguish between human and AI-written text.                | 2023     |
|                                   | GPTZero: An AI Text Detector                                      | [🔗](https://gptzero.me/)                                                            | End-to-end deep learning classifier for detecting AI-generated text.                              | 2023     |
|                                   | DPIC: Decoupling Prompt and Intrinsic Characteristics for LLM Generated Text Detection | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.12519) | Uses contrastive learning to improve detection robustness.                                        | 2023     |
|                                   | Radar: Robust AI-Text Detection via Adversarial Learning          | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2307.03838) | Enhances detection with adversarial training techniques.                                          | 2023     |
|                                   | Multiscale Positive-Unlabeled Detection of AI-Generated Texts     | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.18149) | Introduces multi-scale positive labels for improved detection.                                    | 2023     |
| **Zero-shot Detection (Black Box)**| A Machine Learning Approach to the Automatic Evaluation of Machine Translation | [🔗](https://dl.acm.org/doi/10.3115/1073012.1073032)                               | Utilizes linguistic features for machine translation detection.                                   | 2001     |
|                                   | Release Strategies and the Social Impacts of Language Models      | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/1908.09203) | Examines unigram and bigram features for detection.                                               | 2019     |
|                                   | DNA-GPT: Divergent N-Gram Analysis for Training-Free Detection of GPT-Generated Text | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.17359) | Uses N-gram divergence for training-free detection of GPT-generated text.                         | 2023     |
|                                   | Intrinsic Dimension Estimation for Robust Detection of AI-Generated Texts | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2306.04723) | Explores intrinsic dimensions of text for AI-generated text detection.                            | 2023     |
| **Zero-shot Detection (White Box)**| Detecting Fake Content with Relative Entropy Scoring              | [🔗](https://dl.acm.org/doi/abs/10.5555/3053718.3053722)                            | Uses entropy and log-probability scores to detect machine-generated text. An vivid example is that the word "and" can be followed by many possible words, with "the" being one of the most common successors. In contrast, the phrase "ladies and" typically has fewer plausible continuations, with "gentlemen" being the most likely. Therefore, encountering the phrase "ladies and the" within a text serves as a strong signal of artificial manipulation or forgery. | 2008     |
|                                   | DetectGPT: Zero-Shot Machine-Generated Text Detection Using Probability Curvature | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2301.11305) | Proposes using log probability curvature for detecting model-generated text.                      | 2023     |
|                                   | Efficient Detection of LLM-generated Texts with a Bayesian Surrogate Model | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2305.16617) | Improves efficiency of DetectGPT with Bayesian surrogate models.                                  | 2023     |
|                                   | Fast-DetectGPT: Efficient Zero-Shot Detection of Machine-Generated Text via Conditional Probability Curvature | [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](https://arxiv.org/abs/2310.05130) | Further enhances efficiency with a more efficient sampling step.                                  | 2023     |
                            


## What regulatory strategies can address these negative consequences?
- **[Interim Measures for the Management of Generative Artificial Intelligence Services](https://www.cac.gov.cn/2023-07/13/c_1690898327029107.html):**
  - **Marking Generated Content**: Providers must mark generated content, such as pictures and videos, to prevent public confusion.
  - **Real-Name Verification**: A proposed but omitted measure involved real-name verification for content creators, requiring users to submit identification documents to use the generator, thereby improving content traceability.

## Contributing

Contributions are welcome! If you have any papers that you believe should be included in this list, please submit a pull request with the following information:
- Title
- Authors
- Year
- Link
- Brief description or key findings

Please ensure that your contributions adhere to the existing structure and format of this repository.

## Acknowledgements

We would like to thank Dr. Yunzhen Feng for providing valuable references. If you find this repository helpful, please cite our paper:
```
@misc{xing2024aieatsitselfcaveats,
      title={When AI Eats Itself: On the Caveats of Data Pollution in the Era of Generative AI}, 
      author={Xiaodan Xing and Fadong Shi and Jiahao Huang and Yinzhe Wu and Yang Nan and Sheng Zhang and Yingying Fang and Mike Roberts and Carola-Bibiane Schönlieb and Javier Del Ser and Guang Yang},
      year={2024},
      eprint={2405.09597},
      archivePrefix={arXiv},
      primaryClass={cs.LG},
      url={https://arxiv.org/abs/2405.09597}, 
}
```
## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
