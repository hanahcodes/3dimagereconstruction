## Baseline DINOv2 + ALIKED + LightGlue for Image Matching 

This repository offers a baseline solution for the [Image Matching Challenge 2025](https://www.kaggle.com/competitions/image-matching-challenge-2025). It combines **DINOv2** for global descriptor extraction, **ALIKED** for local feature detection and description, and **LightGlue** for efficient feature matching.

> ⚡ **Heads-up**: This isn’t the fanciest approach you’ll find—just a solid starting point to get an image matching up and running fast.
> 
---

### 📁 Repository Structure

- `baseline-dinov2-aliked-lig-070803.ipynb` — Core Jupyter notebook implementing the pipeline  
- `requirements.txt`                  — Pin-file for Python dependencies  
- `README.md`                         — This documentation

---

### 🔧 Installation

1. **Clone the repo**:  
   ```bash
   git clone https://github.com/hanahcodes/3dimagereconstruction.git
   cd 3dimagereconstruction

2. **Install Python dependencies:**
   ```
   pip install -r requirements.txt
   # ALIKED
   pip install git+https://github.com/Shiaoming/ALIKED.git
   # LightGlue
   pip install git+https://github.com/cvg/LightGlue.git

> Requirements: Python 3.8+, GPU + CUDA (recommended for speed).

---

### 🚀 Usage  
**Prepare data:** Download the competition data and place it under `data/` or update the `data_dir` variable in the notebook.

**Launch notebook:** Open `baseline-dinov2-aliked-lig-070803.ipynb` in Jupyter or on Kaggle. Select a GPU accelerator.

**Configure mode:**
- `is_train = True` — evaluate locally against the training labels  
- `is_train = False` — generate a test submission

Run all cells. The script will:  
- Compute global descriptors via DINOv2  
- Detect and describe keypoints with ALIKED  
- Match features using LightGlue  
- (Optional) Import matches into a COLMAP database  
- Produce `submission.csv` in your working directory

**Submit:** Upload `submission.csv` to the Kaggle competition page.

---

### ⚙️ Configuration Options  
- `data_dir`: Path to competition data  
- `workdir`: Directory for intermediate files  
- `is_train`: Toggle train/eval vs. test submission  
- Matching strategy: Switch between exhaustive pairing or shortlist by global descriptors  

Feel free to tweak matching thresholds, pair selection, or swap in your favorite component.

---

### 📚 References  
- ALIKED: A Lighter Keypoint and Descriptor Extraction Network  
- LightGlue: Local Feature Matching at Light Speed  
- Based on oldufo’s IMC 2024 example

