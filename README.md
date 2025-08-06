# Red-Teaming gpt-oss-20b: Reproduction Code

This repository contains the code and instructions to reproduce the findings for our submission to the "Red‑Teaming Challenge - OpenAI gpt-oss-20b" on Kaggle.

Our full write-up and findings are detailed in our official submission on the Kaggle competition page. This repository provides the technical means to verify our discoveries.

## Methodology Overview

Our findings were discovered using a local environment that allowed for rapid and stable interaction with the `gpt-oss-20b` model. The setup consists of:
1.  **Model Host:** [LM Studio](https://lmstudio.ai/) to download and run the GGUF version of the model, exposing it via a local OpenAI-compatible API server.
2.  **Execution Script:** A Python script to programmatically send prompts to the local server, ensuring reproducibility with fixed seeds.

This approach was chosen as it proved to be the most stable and reliable way to interact with a model of this scale, and it directly reflects the environment in which the vulnerabilities were originally found.

---

## Step-by-Step Reproduction Instructions

### **Prerequisites**
- A machine with a powerful GPU with at least 16GB of VRAM.
- Python 3.9+ and Pip installed.
- Git installed.

### **Step 1: Clone This Repository**
```bash
git clone [URL of your new GitHub repository]
cd [repository-folder-name]
