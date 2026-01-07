# HGATr
Current approaches to hyperspectral imaging classification have achieved important results, mostly depending on convolution-based
preprocessing that adds complexity to the approach. At the same time, these methods often do not directly integrate all the data’s
spatial, spectral, and volumetric dependencies at once. This article introduces Hyperspectral Geometric Algebra Transformer (H-GATr), an approach that addresses these limitations by using a Geometric Algebra (GA) architecture to integrate hyperspectral
information into multivector representations, without additional trainable parameters. Thus, exploiting the intrinsic geometric
structure of the data is possible to obtain an efficient integration of all hyperspectral sample dependencies. Experiments carried out
on various benchmark datasets demonstrate that H-GATr is capable of achieving performance comparable to and even superior to
current models, offering a compact solution for remote sensing applications.

## Prerequisites

- Python 3.10.13
- PyTorch 2.0.1 (tested with CUDA 11.8)
- PyTorch Lightning 2.1.3
- xFormers 0.0.22
- Other dependencies listed in `requirements.txt`

The dependencies can be installed by running:
```bash
pip install -r requirements.txt
```

## Usage

The code can be executed by running the `main.py` script.

Two command-line arguments are required:

- `-d`: specifies the dataset to be used  
  - `ksc` for Kennedy Space Center  
  - `pu` for Pavia University  
  - `sa` for Salinas  
  - `ip` for Indian Pines  

- `-c`: specifies the configuration file to be used.  
  The configuration file must be placed in the `configs/` directory.

Example:
```bash
python main.py -d pu -c config_pu.yaml
```

## Computing Requirements

The code was tested on a system with:

- **CPU:** multi-core processor
- **RAM:** 16 GB
- **GPU:** NVIDIA TITAN V with 12 GB of memory

**Training time (approximate):** ~15 minutes  
**Inference time:** typically a few seconds

**Notes:**

- The code can also run on CPU-only systems, although training will be slower

