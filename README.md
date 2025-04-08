# 🟢 Project Summary

## 📄 Files & Purpose

- **Model Design & Training**
  - `pt_MLP.ipynb`  
    → This file is for model design, training, and conversion to QONNX format.  
    → The converted file is exported as `plz_work.onnx` to the path shown above.

- **FPGA Model Conversion**
  - `n3-build-accelerator-with-finn.ipynb`  
    → This file is used to convert a model for an FPGA board using FINN.
---

## ⚙️ Environment

| Component        | Version   |
|------------------|---------:|
| **CUDA**        | 11.5     |
| **cuDNN**      | 8.3.0    |
| **Conda**      | 22.9.0   |
| **NVIDIA Driver** | 550.120  |
| **Docker** (GPU) | -        |
| **Vitis**      | 2024.1   |
| **FINN**       | -        |

---

## 🧩 Model Structure

| Layer                         | Details                             |
|-------------------------------|------------------------------------:|
| **QuantLinear**               | Input: 50, Output: 128, **8-bit quantization** |
| **BatchNorm**                 | 128                                |
| **ReLU**                      | **8-bit quantization**             |
| **QuantLinear**               | Input: 128, Output: 64, **8-bit quantization** |
| **BatchNorm**                 | 64                                 |
| **ReLU**                      | **8-bit quantization**             |
| **QuantLinear**               | Input: 64, Output: 1, **8-bit quantization** |

---

## 🚀 Optimizer & Training

| Option          | Value   |
|---------------:|:-------:|
| **Optimizer** | Adam    |
| **Epoch**    | 40      |
| **Learning Rate** | 0.001  |
| **Betas**    | (0.9, 0.999) |

---

## 📊 Result

- **Loss**: 0.0810  
- **Accuracy**: 0.9905

---

---

## 🔗 Reference

- [FINN Framework Documentation](https://xilinx.github.io/finn/)
- [Brevitas Library](https://github.com/Xilinx/brevitas)
- [Vitis AI Documentation](https://www.xilinx.com/products/design-tools/vitis/vitis-ai.html)

