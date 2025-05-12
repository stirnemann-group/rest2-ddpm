# REST2 + DDPM Workflow

This repository outlines a workflow enhancing REST2 simulations using Denoising Diffusion Probabilistic Models (DDPM).

## Workflow Overview

The process is divided into three main steps: data preparation, model training, and sample analysis.

### 1. Preparing for Training

**Notebook:** `prepare_for_training.ipynb`

Prepare your training set by processing potential energy data and collective variables.

#### Prerequisites

- **Data Files:**
  - `potential_energy.npy`: A 2D NumPy array `(nstruc, nrep)`, where `energy[i][j]` is the potential energy of structure `i` with the rescaled Hamiltonian of replica `j`.
  - **Collective Variables:** In this example: `d_181_112.npy`, `d_181_221.npy`, `psi_181.npy`, `phi_182.npy`. The model learns `P(d_181_112, d_181_221, psi_181, phi_182, Eddpm)`.

#### Outputs

- `Eddpm.npy`: Rescaled potential energy array `(nrep, nframes)`.
- `training_data_traj.npy`: Stored in `traj_REST2/`. Create this directory beforehand.

### 2. Training and Sample Generation

Execute scripts from [Tiwary Lab's GitHub](https://github.com/tiwarylab/DDPM_REMD) (`run_training.py` and `gen_sample_1.py`), ensuring they're in the same directory as `denoising_diffusion_pytorch/` and `traj_REST2/`.

### 3. Analyzing Generated Samples

**Notebook:** `analyze_generated_samples.ipynb`

Analyze and visualize the generated samples from `results/samples-31_1.npy`.


