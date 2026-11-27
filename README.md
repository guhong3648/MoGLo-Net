<h1 align="center">MoGLo-Net</h1>

<p align="center">
  <strong>Enhancing Free-Hand 3-D Photoacoustic and Ultrasound Reconstruction Using Deep Learning</strong>
</p>

<p align="center">
  <a href="https://doi.org/10.1109/TMI.2025.3579454"><img src="https://img.shields.io/badge/Paper-IEEE%20TMI%202025-97BC43?style=flat-square" alt="Paper: IEEE TMI 2025"></a>
  <a href="#citation"><img src="https://img.shields.io/badge/Citation-BibTeX-307BB5?style=flat-square" alt="Citation: BibTeX"></a>
</p>

<p align="center">
  <strong>SiYeoul Lee<sup>1</sup> · Seonho Kim<sup>1</sup> · MinKyung Seo<sup>1</sup> · SeongKyu Park<sup>1</sup> · Salehin Imrus<sup>1</sup> · Kambaluru Ashok<sup>1</sup> · DongEon Lee<sup>1</sup> · Chunsu Park<sup>2</sup> · SeonYeong Lee<sup>1</sup> · Jiye Kim<sup>1</sup> · Jae-Heung Yoo<sup>3</sup> · MinWoo Kim<sup>2,4</sup></strong>
</p>

<p align="center">
  <sup>1</sup> Department of Information Convergence Engineering, Pusan National University, Yangsan, South Korea<br>
  <sup>2</sup> School of Biomedical Convergence Engineering, Pusan National University, Yangsan, South Korea<br>
  <sup>3</sup> Department of Orthopedic Surgery, Busan Medical Center, Busan, South Korea<br>
  <sup>4</sup> Center for Artificial Intelligence Research, Pusan National University, Busan, South Korea
</p>

<p align="center"><em>IEEE Transactions on Medical Imaging</em>, 44(11), 4652–4665, 2025</p>

MoGLo-Net estimates six-degree-of-freedom probe motion from consecutive B-mode ultrasound images, without an external tracking sensor. It combines patch-wise feature correlation, global-local attention, and recurrent motion estimation. Predicted scan trajectories are used for 3D reconstruction of ultrasound, power Doppler, and photoacoustic images.

---

### Architecture

![MoGLo-Net architecture](fig/fig_DL_Model.png)

### Qualitative Results

**B-mode (in-house)**
![3D ultrasound trajectory comparison 1](fig/fig_US3D_B.png)

**B-mode (public)**
![3D ultrasound trajectory comparison 2](fig/fig_US3D_T1.png)

**Power Doppler**
![3D power Doppler reconstruction](fig/fig_US3D_D.png)

**Photoacoustic imaging**
![3D photoacoustic vascular reconstruction](fig/fig_US3D_P.png)

---

## 1. Environment

The repository includes a Docker-based environment for dependencies such as PyTorch3D.

```bash
# From the host
docker pull guhong3648/guhong:v1
```

The repository also contains a `requirements.txt` file. It reflects the original research environment and includes environment-specific package references, so the Docker image is the simpler starting point.

## 2. Data

The `data/` directory contains a small sample intended to check the data-loading and execution pipeline. **It is not the full dataset used for the paper's training or evaluation.**

The public freehand ultrasound dataset used in the study is available from [Zenodo](https://zenodo.org/records/7740734), with preprocessing details in the [UCL CANDI repository](https://github.com/ucl-candi/freehand). We used the central `320 × 320` region of the original `480 × 640` B-mode frames.

For the public dataset, see:

Q. Li et al., "Trackerless Freehand Ultrasound with Sequence Modelling and Auxiliary Transformation over Past and Future Frames," *IEEE ISBI*, 2023. [DOI](https://doi.org/10.1109/ISBI53787.2023.10230773).

## 3. Repository Structure

```text
US3D/
├── README.md
├── fig/
├── data/                 # Sample data
├── src/                  # Model and experiment code
├── res/                  # Results
└── requirements.txt
```

## Citation

If you use the code or results in your work, please cite:

```bibtex
@article{Lee_2025_MoGLo,
  title   = {Enhancing Free-Hand 3-D Photoacoustic and Ultrasound Reconstruction Using Deep Learning},
  author  = {Lee, SiYeoul and Kim, Seonho and Seo, MinKyung and Park, SeongKyu and Imrus, Salehin and Ashok, Kambaluru and Lee, DongEon and Park, Chunsu and Lee, SeonYeong and Kim, Jiye and Yoo, Jae-Heung and Kim, MinWoo},
  journal = {IEEE Transactions on Medical Imaging},
  volume  = {44},
  number  = {11},
  pages   = {4652--4665},
  year    = {2025},
  doi     = {10.1109/TMI.2025.3579454}
}
```

## Contact

SiYeoul Lee — guhong3648@naver.com
