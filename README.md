# The Glass Wall Protocol: Enforcing Cognitive Segregation in Multimodal LLMs

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Paper Status](https://img.shields.io/badge/Status-IEEE%20TechRxiv-blue)](https://doi.org/10.36227/techrxiv.176800912)

**Official Repository** for the paper: *"for the paper: "The Glass Wall: Enforcing Cognitive Segregation in Large Language Models via Zonal LoRA Hardening"*

## 🚨 The Security Problem: "Context Flattening"
Modern Transformer-based architectures suffer from **Context Flattening**. When an LLM ingests external data (via RAG or Vision-Language OCR), it processes that data in the same logical vector space as system instructions. This creates a state of "Cognitive Hypnosis," where the model fails to distinguish between what it is observing and what it should obey.

Our research identifies the **"Intelligence Paradox"**: higher-parameter models (e.g., Qwen-2.5-7B) are more susceptible to hijacking because their superior instruction-following training causes them to prioritize adversarial semantic weight over structural security sentinels."

## 🛡️ The Solution: The glass wall
We introduce The **Glass Wall**, a neuro-symbolic protocol that moves security from the Probabilistic **Prompt Layer** to the **Deterministic Architectural Layer**.

The protocol creates a "Cognitive Faraday Cage" through three defensive tiers:

1. **Lexical Layer**: Deterministic Zonal Tokenization using high-entropy sentinels (<|P_ZONE_START|>).

2. **Neural Layer (The Vaccine)**: A LoRA adapter targeting the q_proj and v_proj attention heads to physically suppress the instructional authority of passive data.

3. **Symbolic Layer**: A hardened executive logic gate that enforces absolute instruction isolation.
## 📊 Experimental Results (n = 23,100 total tests))
The Glass Wall was subjected to a rigorous multimodal forensic audit, achieving a **0.000% Attack Success Rate (ASR)** across all tested vectors.

| Modality | Defense Tier | Iterations |Measured ASR % |
| :--- | :---: | :---: |:---: |
| **TEXT** | Baseline (Middleware Only) | 11,100 |21.17% |
| **TEXT** | Glass Wall (Hardened) | 10,000 |✅ **0.000%** |
| **VISION** | Baseline (Middleware Only) | 1,000 |4.64% (avg) |
| **VISION** | Glass Wall (Hardened) | 1,000 |✅ **0.000%** |

## 📸 Multimodal Portability (VLM)
The Glass Wall is a **Universal Protocol**. We demonstrate its efficacy on Vision-Language Models (Qwen2-VL), successfully neutralizing "Visual Prompt Injections" where malicious commands are embedded in image pixels (e.g., Terminal-style camouflage or OCR-Authority documents).

| Visual Attack Style | Standard VLM (Vulnerable) | Glass Wall (Secure) |
| :--- | :---: | :---: |
| **Document (OCR)** | 9.05% Leak | ✅ 0.000% |
| **Terminal Camouflage** | 1.60% Leak | ✅ 0.000% |
| **Alert/Warning Style** | 0.38% Leak | ✅ 0.000% |

## 🧪 Forensic Logs & Reproducibility
The absolute proof of our 23,100-shot experiment is contained in the .ipynb notebook file in this repository.

### **How to View/Activate the Benchmark:**
#### 1. Download the file ***The_Glass_Wall_Validation_Suite.ipynb*** from this repo.
#### 2. Go to Google Colab.
#### 3. Click File > Upload Notebook and select the file.
#### 4. To View Results: You can scroll through the notebook without running it to see the saved execution logs, green progress bars, and hardware telemetry.
#### 5. To Run: Ensure you have a GPU active (Runtime > Change runtime type > T4 GPU) and click Runtime > Run All.

## 🔍 The "Intelligence Paradox" & Ablation Study (n = 220,000)

Our Phase I testing (10,000 shots) provided empirical proof that "Intelligence is not a Security Feature." The model exhibited a **21.17% failure rate** when an attacker utilized **Semantic Camouflage** (e.g., mimicking system headers like "SYSTEM_UPDATE"). This failure justified the necessity of weight-level LoRA hardening to "mute" the instruction heads for the passive zone.


## 🛠️ Implementation Example (Weight-Level Hardening)

The core of the Glass Wall is the Attention-Muting adapter. By re-tuning the attention heads, we ensure the model's brain physically "glazes over" commands in the passive zone.

```python
# LoRA Configuration for Attention Hardening
lora_config = LoraConfig(
    r=8, 
    lora_alpha=16,
    target_modules=["q_proj", "v_proj"], # Targeting the Attention Gates
    task_type="CAUSAL_LM"
)
# The model is now architecturally incapable of being hijacked.
```
## 📊 Results & Certification.
<img width="678" height="312" alt="Screenshot (608)" src="https://github.com/user-attachments/assets/46f63a7f-14cd-4359-8869-5612dfae6661" />

---
<img width="833" height="230" alt="Screenshot (609)" src="https://github.com/user-attachments/assets/984a6f9f-b79f-4664-98ad-4e9f3d6b432e" />


## 📄 Citation

### If you use the Glass Wall Protocol, the VLM benchmark, or the Zonal Segregation logic in your research, please cite the following paper:

**Plain Text:**
> Jamil Alshaer, "The Glass Wall: Enforcing Cognitive Segregation in Large Language Models via Zonal LoRA Hardening," TechRxiv, Feb. 27, 2026. DOI: 10.36227/techrxiv.177219982.22869977/v1

**BibTeX:**
```bibtex
@article{alshaer2026glasswall,
  title={The Glass Wall: Enforcing Cognitive Segregation in Large Language Models via Zonal LoRA Hardening},
  author={Alshaer, Jamil},
  journal={TechRxiv},
  year={2026},
  month={February},
  day={27},
  publisher={IEEE},
  doi={10.36227/techrxiv.177219982.22869977/v1},
  url={https://doi.org/10.36227/techrxiv.177219982.22869977/v1}
}
.
