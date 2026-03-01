# Secure Medical DICOM Compression and Encryption Framework

## Overview

This repository provides an end-to-end framework for secure medical image processing, including:

- JPEG2000-based DICOM image compression  
- Residual-based near-lossless reconstruction  
- Post-quantum key exchange using ML-KEM-768 (liboqs)  
- Memristive hyperchaotic image encryption  
- Blockchain-based key integrity validation  
- Runtime performance benchmarking  

The implementation is provided as a Jupyter Notebook and is designed for reproducible academic research.

---

## Repository Structure

```
.
├── main.ipynb
├── requirements.txt
├── LICENSE
└── test_data/
    ├── 256_1.dcm
    ├── 256_2.dcm
    ├── 256_3.dcm
    ├── 800_1.dcm
    ├── 800_2.dcm
    ├── 800_3.dcm
    ├── 960_1.dcm
    ├── 960_2.dcm
    └── 960_3.dcm
```

The `test_data/` folder contains sample DICOM images to allow immediate execution without external dataset downloads.

---

## Installation

### 1. Install Python Dependencies

```bash
pip install -r requirements.txt
```

### 2. Install liboqs (Required for ML-KEM)

System dependencies:

```bash
sudo apt-get install cmake ninja-build gcc g++ libssl-dev
```

Install Python bindings:

```bash
git clone https://github.com/open-quantum-safe/liboqs-python.git
cd liboqs-python
pip install .
```

---

## Running the Code

### Option 1 — Google Colab (Recommended)

1. Upload or clone this repository into Colab.
2. Ensure the `test_data/` folder is available in the runtime.
3. Open `main.ipynb`.
4. Run all cells sequentially.

---

### Option 2 — Local Execution

1. Clone the repository:

```bash
git clone <your-repository-url>
cd <repository-name>
```

2. Launch Jupyter Notebook:

```bash
jupyter notebook
```

3. Open `main.ipynb`.
4. Run all cells.

---

## Dataset Usage

The notebook expects a list of DICOM file paths (`dicom_files`).

Example for using the included test dataset:

```python
import os

dicom_files = []
for f in os.listdir("test_data"):
    if f.endswith(".dcm"):
        dicom_files.append(os.path.join("test_data", f))
```

The framework processes square images of predefined target resolutions (e.g., 256×256, 800×800, 960×960).

---

## Output Metrics

The framework computes:

- Peak Signal-to-Noise Ratio (PSNR)
- Structural Similarity Index (SSIM)
- Compression Ratio (CR)
- Encryption and decryption runtime
- Post-quantum key exchange runtime
- End-to-end execution time

Results are reported as mean ± standard deviation per resolution.

---

## Reproducibility

The provided `test_data/` folder enables full execution without requiring external login or dataset downloads.

All experiments can be reproduced by running the notebook sequentially.

---

## License

This project is released under the MIT License.

---

## Disclaimer

This implementation is intended for academic and research purposes only.