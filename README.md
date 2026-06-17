# Comparative Study of Optimization Algorithms for SLM Fine-Tuning

## Project Overview

This project presents a comprehensive experimental comparison of five optimization algorithms for fine-tuning Small Language Models (SLMs), specifically **DistilBERT**, on a text classification task using the **AG News** dataset.

### Optimizers Evaluated
- **AdamW** – The standard choice for Transformers
- **AdaFactor** – Memory-efficient variant of Adam
- **Lion** – Sign-based optimizer with single momentum state
- **SGD with Momentum** – Classical stochastic gradient descent
- **RMSProp** – Adaptive optimizer for non-stationary objectives

## Key Results

| Optimizer | Test Accuracy | Test F1 | Memory (MB) |
|-----------|---------------|---------|-------------|
| **RMSProp** | **0.931** | **0.931** | 1187.4 |
| SGD-Momentum | 0.928 | 0.928 | 1185.4 |
| AdamW | 0.927 | 0.927 | 1440.6 |
| AdaFactor | 0.923 | 0.923 | **929.4** |
| Lion | 0.922 | 0.922 | 1185.9 |

### Summary
- **RMSProp** achieved the best performance with excellent stability.
- **AdamW** remains reliable but is the most memory-intensive.
- **AdaFactor** is the most memory-efficient but requires careful tuning.
- **Lion** showed the lowest performance despite memory advantages.

## Requirements

Python 3.8+
PyTorch
Transformers
Datasets
Lion-Pytorch
Scikit-learn
Matplotlib
Pandas

## Repository Structure


├── comparaison-optimisateurs.ipynb   # Main Jupyter Notebook
├── README.md

## How to Run

1. **Clone the repository**
```bash
git clone https://github.com/SalamaBsd/optimization-algorithms-slm-finetuning
cd optimization-algorithms-slm-finetuning
```

2. **Install dependencies**
```bash
pip install -q transformers datasets accelerate evaluate lion-pytorch scikit-learn matplotlib pandas
```

3. **Run the notebook**
```bash
jupyter notebook comparaison-optimisateurs.ipynb
```

## Generated Results

The notebook automatically generates:
- Comparative performance tables
- Loss and accuracy evolution curves
- Resource consumption bar charts
- Learning rate sensitivity plots
- Multi-seed stability analysis

## Key Findings

- **RMSProp** emerges as the best overall optimizer for this setup.
- **AdaFactor** is recommended for memory-constrained environments.
- **AdamW** is a safe choice but consumes the most memory.
- **Lion** requires careful tuning and showed lower performance.
- **SGD-M** can perform well but is highly sensitive to learning rates.

## Authors

- BOUSSAID Salama
- CHAABAN Malika
- BOUNADAR Douaa

## Supervision

- **Pr. Faouzia Benabbou**
- Master Intelligence Artificielle - FSBM
- Module Optimization
- Academic Year: 2025-2026

## References

```bibtex
@inproceedings{kingma2015adam,
  title={Adam: A Method for Stochastic Optimization},
  author={Kingma, Diederik P and Ba, Jimmy},
  booktitle={ICLR},
  year={2015}
}

@article{sanh2019distilbert,
  title={DistilBERT, a distilled version of BERT},
  author={Sanh, Victor and Debut, Ly and Chaumond, Julien and Wolf, Thomas},
  journal={arXiv:1910.01108},
  year={2019}
}

@inproceedings{loshchilov2019decoupled,
  title={Decoupled Weight Decay Regularization},
  author={Loshchilov, Ilya and Hutter, Frank},
  booktitle={ICLR},
  year={2019}
}

@inproceedings{shazeer2018adafactor,
  title={Adafactor: Adaptive Learning Rates with Sublinear Memory Cost},
  author={Shazeer, Noam and Stern, Mitchell},
  booktitle={ICML},
  year={2018}
}

@inproceedings{chen2023symbolic,
  title={Symbolic Discovery of Optimization Algorithms},
  author={Chen, Xiangning and Liang, Chen and Huang, Da and Real, Esteban and Wang, Kai and Pham, Hieu and Xu, Yifeng and Le, Quoc V},
  booktitle={NeurIPS},
  year={2023}
}
```

## License

This project is for educational purposes as part of the Master Intelligence Artificielle program at FSBM.
```
