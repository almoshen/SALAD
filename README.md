# 🥗 SALAD: Part-Level Latent Diffusion for 3D Shape Generation and Manipulation, ICCV 2023

![teaser](./docs/images/salad_teaser.png)


[**Arxiv**](https://arxiv.org/abs/2303.12236) | [**Project Page**](https://salad3d.github.io/) <br>

[Juil Koo\*](https://63days.github.io/), [Seungwoo Yoo\*](https://dvelopery0115.github.io/), [Minh Hieu Nguyen\*](https://min-hieu.github.io/), [Minhyuk Sung](https://mhsung.github.io/) <br>
\* denotes equal contribution.


# Introduction
This repository contains the official implementation of 🥗 **SALAD: Part-Level Latent Diffusion for 3D Shape Generation and Manipulation**.<br>
**SALAD** is a 3D shape diffusion model which generates high-quality shapes and hints its zero-shot capability in various shape manipulation applications. More results can be viewed with a 3D viewer on the [project webpage](https://salad3d.github.io).

# Get Started

## Installation

For main requirements, we have tested the code with Python 3.9, CUDA 11.3 and Pytorch 1.12.1+cu113.

```
git clone https://github.com/63days/salad/
cd SALAD
conda env create -f environment.yml
conda activate salad
pip install -e .
```

## Data and Model Checkpoint
We provide ready-to-use data and pre-trained SALAD and SPAGHETTI checkpoints [here](https://1drv.ms/f/s!AtxL_EOxFeYMk0s3rDbhJORZ6ITD?e=VA09ei). 
Unzip files and put them under the corresponding directories. SPAGHETTI checkpoint directoriess should be under the `SALAD/salad/spaghetti/assets/checkpoints/` directory.


# Training
## Unconditional Generation

You can train models for unconditional generation with airplanes, chairs or tables.
```
python train.py model={phase1, phase2} category={airplane, chair, table}
```

## Text-Guided Generation

For text-guided generation, train a first-phase model and a second-phase model:
```
python train.py model={lang_phase1, lang_phase2}
```

# Demo
## Unconditional Shape Generation

We provide the demo code of unconditional generation with airplanes, chairs and tables at `notebooks/unconditional_generation_demo.ipynb`.

## Text-Guided Shape Generation

We also provide text-guided shape generation demo code at `notebooks/text_generation_demo.ipynb`.


# Citation
If you find our work useful, please consider citing:

```bibtex
@article{koo2023salad,
    title={{SALAD}: Part-Level Latent Diffusion for 3D Shape Generation and Manipulation},
    author={Koo, Juil and Yoo, Seungwoo and Nguyen, Minh Hieu and Sung, Minhyuk},
    year={2023},
    journal={arXiv preprint arXiv:2303.12236},
}
```

# Reference
We borrow [SPAGHETTI](https://amirhertz.github.io/spaghetti/) code from the [official implementation](https://github.com/amirhertz/spaghetti).
