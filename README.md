# Diffusion‑Models

> **VAE · VQ‑VAE · β‑VAE · ELBO · GFlow · DDPM · DALL·E**
> *A playground for learning and comparing modern generative models for AI artwork.*

![Last Commit](https://img.shields.io/github/last-commit/jhlucc/Diffusion-Models)
![Stars](https://img.shields.io/github/stars/jhlucc/Diffusion-Models)
![License](https://img.shields.io/github/license/jhlucc/Diffusion-Models)

---

## 📖 项目简介 | Overview

本仓库收集并实现了 **Diffusion & VAE 系列** 的代表性生成模型，适用于：

* 快速上手 AI 绘图 / 图像生成
* 学习不同生成范式（扩散、变分、流）的核心思想
* 横向比较各模型在同一数据集上的效果

每个子模型目录均包含 **Jupyter Notebook** 演示与关键 **PyTorch** 代码，方便边学边改。

---

## 🗂️ 目录结构 | Repository Structure

| 路径          | 描述                                      | 典型内容                           |
| ----------- | --------------------------------------- | ------------------------------ |
| `Beta‑VAE/` | β‑VAE 变分自编码器                            | `create_beta_vae.py`, Notebook |
| `VAE/`      | Vanilla VAE                             | 训练 / 采样脚本                      |
| `VQ‑VAE/`   | 向量量化 VAE                                | `create_vq_vae.py`             |
| `ELBO/`     | 变分下界推导                                  | 数学笔记 & 代码                      |
| `Gflow/`    | GFlow 基于流的生成                            | Glow / Flow‑based 示例           |
| `DDPM/`     | Denoising Diffusion Probabilistic Model | 训练 & 推断                        |
| `DALLE/`    | DALL·E 简化复现                             | 编码器 + Transformer              |
| `ai路线.txt`  | 个人学习路线笔记                                | ——                             |
| `*.md`      | 论文解读 / 理论笔记                             | ——                             |
| `LICENSE`   | Apache‑2.0 许可证                          | ——                             |

---

## 🚀 快速开始 | Quick Start

```bash
# 1️⃣ 克隆仓库
git clone https://github.com/jhlucc/Diffusion-Models.git
cd Diffusion-Models

# 2️⃣ 创建 Conda / venv 环境 (Python ≥ 3.8)
conda create -n dm_env python=3.9
conda activate dm_env

# 3️⃣ 安装依赖
pip install -r requirements.txt      # 若尚未提供，可参考下方常用包
# pip install torch torchvision torchaudio
# pip install matplotlib numpy tqdm scikit-learn pillow einops

# 4️⃣ 运行 Notebook
jupyter lab
# 5️⃣ 或直接运行脚本（以 DDPM 为例）
python DDPM/train_ddpm.py --cfg configs/ddpm_cifar10.yaml
```

---

## 🖼️ 数据集 | Datasets

示例 Notebook 默认使用 **CIFAR‑10 / MNIST / CelebA** 等公开数据集，可在首次运行时自动下载。
若要替换为自定义数据集，请修改对应目录下的 `config/*.yaml` 或 Notebook 中的数据加载路径。

---

## 🧠 已实现模型 | Implemented Models

| 类别         | 模型列表                         |
| ---------- | ---------------------------- |
| **VAE 系列** | VAE · β‑VAE · VQ‑VAE         |
| **扩散模型**   | DDPM · DDIM *(计划)*           |
| **流式模型**   | Glow / GFlow                 |
| **文本到图像**  | DALL·E（VQ‑VAE + Transformer） |
| **理论推导**   | ELBO、KL 散度、重参数化技巧            |

---

## 📊 评估指标 | Metrics

* **定量**：FID, IS, reconstruction MSE
* **定性**：随机采样 / 重建对比图
* **训练监控**：TensorBoard & WandB 支持

---

## 📌 TODO

* [ ] 集成 DDIM、Score‑based SDE
* [ ] 增加 **LDM / Stable Diffusion** 微型实现
* [ ] 自动化对比实验脚本 & 结果表
* [ ] Docker 镜像、一键部署

---

## 🤝 贡献 | Contributing

1. **Fork** → 新建分支 → **PR**
2. 保持代码风格（`black` / `flake8`）
3. Notebook 请确保自顶向下可复现，PR 附示例图或日志

---

## 📝 参考文献 | References

* Kingma & Welling. *Auto‑Encoding Variational Bayes*, ICLR 2014
* Ho *et al.* *Denoising Diffusion Probabilistic Models*, NeurIPS 2020
* Rombach *et al.* *High‑Resolution Image Synthesis with Latent Diffusion Models*, CVPR 2022
* van den Oord *et al.* *Neural Discrete Representation Learning*, NeurIPS 2017
 
---

## ⚖️ 许可证 | License

本项目采用 **Apache‑2.0** 许可证。详见 [LICENSE](./LICENSE)。

---

## 📬 联系方式 | Contact

* **Author**: [@jhlucc](https://github.com/jhlucc)

如果本仓库对你有帮助，欢迎 **Star ⭐**、提 Issue 或 PR！
