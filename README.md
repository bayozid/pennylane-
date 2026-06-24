# PennyLane Quantum Computing Tutorials

A comprehensive collection of Jupyter notebooks demonstrating quantum computing concepts using **PennyLane**, a cross-platform Python library for quantum machine learning and quantum computing.

## 📚 Overview

This repository contains practical tutorials and examples for learning quantum computing with PennyLane, from foundational concepts to advanced applications like training quantum circuits classically and deploying quantum algorithms.

## 📋 Contents

### 1. **pennylabeSDK.ipynb** - PennyLane Fundamentals
An introductory guide covering:
- **Quantum Functions & QNodes**: Learn how to define quantum circuits
- **Devices**: Understanding simulators (default.qubit, lightning.qubit)
- **Templates**: Using built-in quantum templates like BasisEmbedding
- **Circuit Decomposition**: Breaking down quantum templates into basic gates (Clifford+T gates)
- **Debugging Tips**: Best practices for working with quantum circuits

### 2. **Classical_Deploying_Quantum.ipynb** - Classical Training of Quantum Circuits
Demonstrates how to optimize quantum circuits using classical methods:
- Monte Carlo sampling for expectation value estimation
- Exact quantum simulation using PennyLane devices
- Classical parameter optimization with JAX and Optax
- Gradient-based training using automatic differentiation
- Resource estimation for quantum circuits
- Integration with modern ML frameworks (JAX, Optax)

### 3. **pennylane_classical_deploy_quantum.ipynb** - Advanced Quantum Optimization
Builds on quantum-classical hybrid approaches:
- Setting up quantum circuits with parametrized gates
- Classical optimization of quantum circuit parameters
- Using IQP (Instantaneous Quantum Polynomial) templates
- Training quantum circuits for specific observables

## 🔧 Technologies

- **PennyLane** (v0.45.0+): Quantum computing framework
- **JAX**: Automatic differentiation and functional programming
- **Optax**: Gradient-based optimization
- **NumPy/SciPy**: Numerical computing
- **Jupyter**: Interactive notebooks

## 📦 Installation

### Prerequisites
- Python 3.10+
- pip or conda

### Setup

```bash
# Clone the repository
git clone https://github.com/bayozid/pennylane-.git
cd pennylane-

# Install dependencies
pip install pennylane optax jax jaxlib numpy scipy

# Or use conda
conda install -c conda-forge pennylane optax jax jaxlib
```

## 🚀 Getting Started

1. **Start with the basics**:
   ```bash
   jupyter notebook pennylabeSDK.ipynb
   ```

2. **Learn classical quantum training**:
   ```bash
   jupyter notebook Classical_Deploying_Quantum.ipynb
   ```

3. **Explore advanced techniques**:
   ```bash
   jupyter notebook pennylane_classical_deploy_quantum.ipynb
   ```

## 💡 Key Concepts

### Quantum Circuits
Define quantum functions with gates and measurements:
```python
import pennylane as qp

dev = qp.device("default.qubit")

@qp.qnode(dev)
def circuit(params):
    qp.RX(params[0], wires=0)
    qp.CNOT(wires=[0, 1])
    return qp.expval(qp.Z(0))
```

### Quantum-Classical Hybrid
Train quantum circuits using classical optimizers:
- Use `qp.qnn.iqp_expval()` for Monte Carlo estimation
- Integrate with JAX for automatic differentiation
- Use Optax for gradient-based optimization

### Resource Estimation
Analyze quantum circuit complexity:
```python
resources = qp.estimator.estimate(circuit)
# Shows gate counts, wire usage, and T-gate requirements
```

## 📖 Learning Path

| Level | Topic | Notebook |
|-------|-------|----------|
| Beginner | PennyLane Basics | pennylabeSDK.ipynb |
| Intermediate | Quantum-Classical Hybrid Training | Classical_Deploying_Quantum.ipynb |
| Advanced | Circuit Optimization | pennylane_classical_deploy_quantum.ipynb |

## 🎯 Use Cases

- **Quantum Machine Learning**: Train quantum circuits as machine learning models
- **Circuit Optimization**: Minimize gate counts and resource requirements
- **Variational Algorithms**: Implement QAOA, VQE, and other variational methods
- **Research**: Explore quantum computing without access to real hardware

## ⚙️ Requirements

- PennyLane >= 0.41.0
- JAX >= 0.5.3
- Optax >= 0.2.0
- NumPy >= 2.0
- SciPy >= 1.14

## 📝 License

This project is open source and available for educational purposes.

## 🔗 Resources

- [PennyLane Documentation](https://pennylane.ai/)
- [PennyLane Tutorials](https://pennylane.ai/qml/tutorials/)
- [JAX Documentation](https://jax.readthedocs.io/)
- [Quantum Computing Basics](https://pennylane.ai/qml/quantum_intro/)

## 👤 Author

**bayozid** - Quantum Computing Enthusiast

---

**Happy Quantum Computing! 🚀⚛️**
