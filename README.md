# CodeTalker
Speech-Driven 3D Facial Animation with Discrete Motion Prior
# Step-by-Step Guide for Running the Speech-Driven 3D Facial Animation Project in Google Colab

This guide provides detailed instructions on how to set up, run, and replicate the **CodeTalker: Speech-Driven 3D Facial Animation with Discrete Motion Prior** project using Google Colab.

---

## 1. **Setting Up Google Colab**

1. Open [Google Colab](https://colab.research.google.com).
2. In the top menu, navigate to **Edit** > **Notebook settings**.
3. Under the **Hardware accelerator** section, select **GPU** and save the settings.

---

## 2. **Environment Setup**

### Step 1: Verify GPU Availability

Run the following command to confirm that the GPU is available:

```bash
!nvidia-smi --query-gpu=name,memory.total,memory.free --format=csv,noheader
```

### Step 2: Install Python 3.8

Google Colab uses Python 3.10 by default, so you need to switch to Python 3.8:

```bash
!sudo apt-get install python3.8-distutils python3.8-dev python3.8
!python --version
!sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
!sudo update-alternatives --config python3
```

When prompted, select the index corresponding to Python 3.8.

### Step 3: Install Required Libraries

Run the following commands to install the necessary dependencies:

```bash
!sudo dpkg --remove --force-remove-reinstreq python3-pip python3-setuptools python3-wheel
!apt-get install python3-pip
!pip install torch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0
!pip install einops numpy librosa==0.8.1 tqdm trimesh==3.9.27 scipy==1.7.2
!pip install pyrender pyopengl==3.1.5 pyglet==1.5.27 opencv-python glfw
!pip install transformers==4.6.1
```

Install additional system libraries:

```bash
!apt-get install libboost-dev python3-opengl libosmesa6-dev libgl1-mesa-dev libglfw3-dev libeigen3-dev mesa-utils
```

---

## 3. **Download Resources**

Clone the project repository and install any required submodules:

```bash
!git clone https://github.com/Doubiiu/CodeTalker.git
!export PYTHONPATH=/content/CodeTalker:$PYTHONPATH
```

Download pretrained model weights and templates for VOCASET and BIWI datasets:

```bash
!gdown --id '1RszIMsxcWX7WPlaODqJvax8M_dnCIzk5' --output vocaset/vocaset_stage1.pth.tar
!gdown --id '1phqJ_6AqTJmMdSq-__KY6eVwN4J9iCGP' --output vocaset/vocaset_stage2.pth.tar
!gdown --id '1rN7pXRzfROwTMcBeOA7Qju6pqy2rxzUX' --output vocaset/templates.pkl
!gdown --id '1FSxey5Qug3MgAn69ymwFt8iuvwK6u37d' --output BIWI/biwi_stage1.pth.tar
!gdown --id '1gSNo9KYeIf6Mx3VYjRXQJBcg7Qv8UiUl' --output BIWI/biwi_stage2.pth.tar
!gdown --id '1Q2UnLwf0lg_TTYe9DdR3iJM2aSGF45th' --output BIWI/templates.pkl
```

# Step-by-Step Guide for Running the Speech-Driven 3D Facial Animation Project in Google Colab

This guide provides detailed instructions on how to set up, run, and replicate the **CodeTalker: Speech-Driven 3D Facial Animation with Discrete Motion Prior** project using Google Colab.

---

## 1. **Setting Up Google Colab**

1. Open [Google Colab](https://colab.research.google.com).
2. In the top menu, navigate to **Edit** > **Notebook settings**.
3. Under the **Hardware accelerator** section, select **GPU** and save the settings.

---

## 2. **Environment Setup**

### Step 1: Verify GPU Availability

Run the following command to confirm that the GPU is available:

```bash
!nvidia-smi --query-gpu=name,memory.total,memory.free --format=csv,noheader
```

### Step 2: Install Python 3.8

Google Colab uses Python 3.10 by default, so you need to switch to Python 3.8:

```bash
!sudo apt-get install python3.8-distutils python3.8-dev python3.8
!python --version
!sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
!sudo update-alternatives --config python3
```

When prompted, select the index corresponding to Python 3.8.

### Step 3: Install Required Libraries

Run the following commands to install the necessary dependencies:

```bash
!sudo dpkg --remove --force-remove-reinstreq python3-pip python3-setuptools python3-wheel
!apt-get install python3-pip
!pip install torch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0
!pip install einops numpy librosa==0.8.1 tqdm trimesh==3.9.27 scipy==1.7.2
!pip install pyrender pyopengl==3.1.5 pyglet==1.5.27 opencv-python glfw
!pip install transformers==4.6.1
```
Here’s the content formatted in Markdown, ready to be pasted into your README file:

---

## **New Dependencies Added**

### **1. Python 3.8 Installation**
The following commands were added to install Python 3.8 and ensure compatibility with the environment:

```bash
!sudo apt-get install python3.8-distutils
!sudo apt-get install python3.8-dev
!sudo apt-get install python3.8
```

---

### **2. OpenGL and Rendering Libraries**

Additional commands were included to install and upgrade OpenGL and other rendering-related libraries:

```bash
!pip install --upgrade librosa
!pip install pyrender
!apt-get install libosmesa6-dev
!apt-get install libgl1-mesa-dev
!apt-get install libglfw3-dev
!pip install glfw
!apt-get install libeigen3-dev
!apt-get install mesa-utils
!pip install --upgrade PyOpenGL
```

---

### **3. Notes**
- Ensure these dependencies are installed in the Colab environment before running the project.
- The upgrades improve rendering and compatibility for the 3D facial animation generation process.

--- 

This can now be directly added to your README file. Let me know if you need further refinements!

## 3. **Download Resources**

Clone the project repository and install any required submodules:

```bash
!git clone https://github.com/Doubiiu/CodeTalker.git
!export PYTHONPATH=/content/CodeTalker:$PYTHONPATH
```

Download pretrained model weights and templates for VOCASET and BIWI datasets:

```bash
!gdown --id '1RszIMsxcWX7WPlaODqJvax8M_dnCIzk5' --output vocaset/vocaset_stage1.pth.tar
!gdown --id '1phqJ_6AqTJmMdSq-__KY6eVwN4J9iCGP' --output vocaset/vocaset_stage2.pth.tar
!gdown --id '1rN7pXRzfROwTMcBeOA7Qju6pqy2rxzUX' --output vocaset/templates.pkl
!gdown --id '1FSxey5Qug3MgAn69ymwFt8iuvwK6u37d' --output BIWI/biwi_stage1.pth.tar
!gdown --id '1gSNo9KYeIf6Mx3VYjRXQJBcg7Qv8UiUl' --output BIWI/biwi_stage2.pth.tar
!gdown --id '1Q2UnLwf0lg_TTYe9DdR3iJM2aSGF45th' --output BIWI/templates.pkl
```

---

## 4. **Running Pre-Built Demos**

### VOCASET Demo

Run the following commands to generate and render a demo animation using the VOCASET dataset:

```bash
!sh scripts/demo.sh vocaset
```

### BIWI Demo

Run the following commands for the BIWI dataset:

```bash
!sh scripts/demo.sh BIWI
```

---

## 5. **Generating Custom Animations**

### Step 1: Upload Your Audio File

In Colab, upload a `.wav` file (duration around 10 seconds):

```python
from google.colab import files
uploaded = files.upload()
filename = list(uploaded.keys())[0]
print(filename)
```

### Step 2: Select Dataset, Style, and Subject

Use the following interactive widget to select your dataset, style, and subject:

```python
from ipywidgets import interact, Select
vocaset_style = ['FaceTalk_170728_03272_TA', 'FaceTalk_170904_00128_TA', ...]
vocaset_subject = ['FaceTalk_170809_00138_TA', 'FaceTalk_170731_00024_TA', ...]
biwi_style = ['F2', 'F3', 'F4', ...]
biwi_subject = ['F1', 'F5', 'F6', ...]

def update_otherW_options(*args):
    styleW.options = dataset[datasetW.value][0]
    subjectW.options = dataset[datasetW.value][1]

@interact(dataset=datasetW, style=styleW, subject=subjectW)
def print_options(dataset, style, subject):
    print(f"Dataset: {dataset}, Style: {style}, Subject: {subject}")
```

### Step 3: Generate Animation

Modify the configuration file with your selections and generate the animation:

```bash
!sh scripts/demo.sh <dataset_name>
```

---

## 6. **Viewing Outputs**

View the generated animation directly in Colab:

```python
from IPython.display import HTML
from base64 import b64encode
mp4_name = 'demo/output/<filename>_<subject>_condition_<style>_audio.mp4'
mp4 = open(mp4_name, 'rb').read()
data_url = "data:video/mp4;base64," + b64encode(mp4).decode()
HTML(f'<video width=600 controls><source src="{data_url}" type="video/mp4"></video>')
```

---

## Notes

- Ensure that the Python version is correctly set to 3.8 throughout.
- Make sure all dependencies are installed and GPU is enabled for faster rendering.
- If any error occurs, refer to the error logs and ensure all necessary packages are installed.

This step-by-step guide ensures reproducibility for anyone working on this project in Google Colab.



---

## 4. **Running Pre-Built Demos**

### VOCASET Demo

Run the following commands to generate and render a demo animation using the VOCASET dataset:

```bash
!sh scripts/demo.sh vocaset
```

### BIWI Demo

Run the following commands for the BIWI dataset:

```bash
!sh scripts/demo.sh BIWI
```

---

## 5. **Generating Custom Animations**

### Step 1: Upload Your Audio File

In Colab, upload a `.wav` file (duration around 10 seconds):

```python
from google.colab import files
uploaded = files.upload()
filename = list(uploaded.keys())[0]
print(filename)
```

### Step 2: Select Dataset, Style, and Subject

Use the following interactive widget to select your dataset, style, and subject:

```python
from ipywidgets import interact, Select
vocaset_style = ['FaceTalk_170728_03272_TA', 'FaceTalk_170904_00128_TA', ...]
vocaset_subject = ['FaceTalk_170809_00138_TA', 'FaceTalk_170731_00024_TA', ...]
biwi_style = ['F2', 'F3', 'F4', ...]
biwi_subject = ['F1', 'F5', 'F6', ...]

def update_otherW_options(*args):
    styleW.options = dataset[datasetW.value][0]
    subjectW.options = dataset[datasetW.value][1]

@interact(dataset=datasetW, style=styleW, subject=subjectW)
def print_options(dataset, style, subject):
    print(f"Dataset: {dataset}, Style: {style}, Subject: {subject}")
```

### Step 3: Generate Animation

Modify the configuration file with your selections and generate the animation:

```bash
!sh scripts/demo.sh <dataset_name>
```

---

## 6. **Viewing Outputs**

View the generated animation directly in Colab:

```python
from IPython.display import HTML
from base64 import b64encode
mp4_name = 'demo/output/<filename>_<subject>_condition_<style>_audio.mp4'
mp4 = open(mp4_name, 'rb').read()
data_url = "data:video/mp4;base64," + b64encode(mp4).decode()
HTML(f'<video width=600 controls><source src="{data_url}" type="video/mp4"></video>')
```

---

## Notes

- Ensure that the Python version is correctly set to 3.8 throughout.
- Make sure all dependencies are installed and GPU is enabled for faster rendering.
- If any error occurs, refer to the error logs and ensure all necessary packages are installed.




Here’s a detailed, step-by-step guide for running the project on a **local machine**, written for users without prior knowledge, and formatted for direct inclusion in a README file:

---

# **Step-by-Step Guide for Running the Speech-Driven 3D Facial Animation Project on a Local Machine**

This guide provides detailed instructions to set up and execute the **CodeTalker: Speech-Driven 3D Facial Animation with Discrete Motion Prior** project on a local machine.

---

## **1. System Requirements**

Before proceeding, ensure your system meets the following requirements:
- **Operating System**: Linux, macOS, or Windows Subsystem for Linux (WSL).
- **Python Version**: 3.8 (strictly required).
- **GPU with CUDA Support** (optional but recommended for faster execution).

---

## **2. Step-by-Step Installation**

### **Step 1: Install Python 3.8**

If Python 3.8 is not already installed, follow these steps:

#### On Ubuntu:
```bash
sudo apt-get update
sudo apt-get install python3.8 python3.8-distutils python3.8-dev
```

#### On Windows (using WSL or standalone):
1. Download Python 3.8 from the official [Python website](https://www.python.org/downloads/release/python-380/).
2. Follow the installation instructions and ensure **pip** is included in the installation.

#### On macOS:
```bash
brew install python@3.8
```

---

### **Step 2: Set Python 3.8 as Default**

Switch to Python 3.8 if multiple Python versions are installed:

```bash
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
sudo update-alternatives --config python3
```

Verify the version:
```bash
python3 --version
```

---

### **Step 3: Install System Libraries**

Install required system libraries for OpenGL and rendering support:

```bash
sudo apt-get install libosmesa6-dev libgl1-mesa-dev libglfw3-dev libeigen3-dev mesa-utils libboost-dev python3-opengl
```

---

### **Step 4: Install Python Dependencies**

Install `pip` and use it to install Python libraries:

```bash
sudo apt-get install python3-pip
pip install --upgrade pip
pip install torch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0
pip install einops numpy librosa==0.8.1 tqdm trimesh==3.9.27 scipy==1.7.2 pyrender pyopengl==3.1.5 pyglet==1.5.27 opencv-python glfw transformers
```

---

## **3. Download and Set Up the Project**

### **Step 1: Clone the Repository**

Clone the CodeTalker repository to your local machine:

```bash
git clone https://github.com/Doubiiu/CodeTalker.git
cd CodeTalker
```

### **Step 2: Download Pretrained Models**

Download the pretrained model weights and templates required for the VOCASET and BIWI datasets:

```bash
wget -O vocaset/FLAME_sample.ply https://github.com/TimoBolkart/voca/raw/master/template/FLAME_sample.ply
gdown --id '1RszIMsxcWX7WPlaODqJvax8M_dnCIzk5' --output vocaset/vocaset_stage1.pth.tar
gdown --id '1phqJ_6AqTJmMdSq-__KY6eVwN4J9iCGP' --output vocaset/vocaset_stage2.pth.tar
gdown --id '1rN7pXRzfROwTMcBeOA7Qju6pqy2rxzUX' --output vocaset/templates.pkl
gdown --id '1FSxey5Qug3MgAn69ymwFt8iuvwK6u37d' --output BIWI/biwi_stage1.pth.tar
gdown --id '1gSNo9KYeIf6Mx3VYjRXQJBcg7Qv8UiUl' --output BIWI/biwi_stage2.pth.tar
gdown --id '1Q2UnLwf0lg_TTYe9DdR3iJM2aSGF45th' --output BIWI/templates.pkl
```

---

## **4. Running Pre-Built Demos**

### **Step 1: VOCASET Demo**

To generate and render a demo animation using the VOCASET dataset:

```bash
sh scripts/demo.sh vocaset
```

### **Step 2: BIWI Demo**

To generate and render a demo animation using the BIWI dataset:

```bash
sh scripts/demo.sh BIWI
```

---

## **5. Generate Custom Animations**

### **Step 1: Prepare Your Audio File**

1. Place your `.wav` file in the `demo/wav/` directory.
2. Ensure the duration is around **10 seconds** for best results.

### **Step 2: Modify the Configuration**

Update the configuration file (`config/vocaset/demo.yaml` or `config/BIWI/demo.yaml`) with:
- **Dataset**: Select VOCASET or BIWI.
- **Style and Subject**: Choose from the predefined options.
- **Audio File Path**: Set the path to your `.wav` file.

Example snippet in `demo.yaml`:
```yaml
condition: FaceTalk_170725_00137_TA
subject: FaceTalk_170809_00138_TA
demo_wav_path: demo/wav/your_audio_file.wav
```

### **Step 3: Generate Animation**

Run the following command to render the animation:

```bash
sh scripts/demo.sh <dataset_name>
```

Replace `<dataset_name>` with `vocaset` or `BIWI` as per your configuration.

---

## **6. Viewing Outputs**

### **Step 1: Locate the Output**

The rendered animation will be saved in the `demo/output/` directory.

### **Step 2: Play the Video**

You can view the video using any media player that supports `.mp4` files.

```bash
xdg-open demo/output/<generated_video>.mp4
```

---

## **7. Troubleshooting**

1. **Python Version Issues**:
   - Ensure Python 3.8 is correctly installed and set as default.

2. **Dependency Installation Errors**:
   - Use `apt-get` to install missing system libraries.
   - Use `pip install` to resolve Python library errors.

3. **GPU Not Detected**:
   - Check CUDA installation with `nvidia-smi`.

4. **Rendering Issues**:
   - Verify OpenGL compatibility by running `glxinfo | grep "OpenGL version"`.

---
