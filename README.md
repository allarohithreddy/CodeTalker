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
