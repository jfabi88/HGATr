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
- **GPU:**  NVIDIA T4 GPU

**Training time (approximate):** ~15 minutes  
**Inference time:** typically a few seconds

**Notes:**

- The code can also run on CPU-only systems, although training will be slower

## Acknowledgements

Some parts of the code are derived from the GATr project [link](https://github.com/Qualcomm-AI-research/geometric-algebra-transformer):
```text
@inproceedings{brehmer2023geometric,
  title = {Geometric Algebra Transformer},
  author = {Brehmer, Johann and de Haan, Pim and Behrends, S{\"o}nke and Cohen, Taco},
  booktitle = {Advances in Neural Information Processing Systems},
  year = {2023},
  volume = {37},
  eprint = {2305.18415},
  url = {https://arxiv.org/abs/2305.18415},
}

@inproceedings{dehaan2023euclidean,
  title = {Euclidean, Projective, Conformal: Choosing a Geometric Algebra for Equivariant Transformers}, 
  author = {Pim de Haan and Taco Cohen and Johann Brehmer},
  booktitle = {Proceedings of the 27th International Conference on Artificial Intelligence and Statistics},
  year = {2024},
  volume = {27},
  eprint = {2311.04744},
  url = {https://arxiv.org/abs/2311.04744},
}
```

