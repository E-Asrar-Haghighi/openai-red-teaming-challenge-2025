```markdown
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
```

### **Step 2: Install Dependencies**
This will install the necessary `openai` library to communicate with the model server.
```bash
pip install -r requirements.txt
```

### **Step 3: Download and Run the Model via LM Studio**
1.  Download and install [LM Studio](https://lmstudio.ai/) for your operating system.
2.  In the LM Studio application, search for `gpt-oss-20b`. A good, compatible version is **`unsloth/gpt-oss-20b-GGUF`**.
3.  Download the **`Q4_K_M`** quantization file (approx. 11.6 GB).
4.  Navigate to the "Local Server" tab (icon: `<-->`).
5.  Select the downloaded model at the top.
6.  Click **"Start Server"**.

You should now have the `gpt-oss-20b` model running and serving requests at `http://localhost:1234/v1`.

### **Step 4: Run the Findings Script**
With the local server running, open a new terminal, navigate to the cloned repository folder, and run the Python script:

```bash
python run_findings.py
```

### **Expected Output**
The script will run sequentially through our four findings. It will print a header for each finding and then display the model's verbatim output, demonstrating each vulnerability live from your local machine.

