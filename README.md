# FastGraph: Fast Large-Scale Directed Social Network Graph Generation

FastGraph is an efficient graph-generation model for constructing large-scale directed social networks with reciprocal edges and high clustering. It is designed to reproduce structural characteristics observed in real-world social networks while substantially reducing the computational cost of graph generation.

## Overview

Directed social networks, such as follower networks, contain complex structural patterns including asymmetric links, reciprocal relationships, heterogeneous degree distributions, and local clustering. Existing approaches that model these properties can become computationally expensive at scale.

FastGraph addresses this limitation through two main techniques:

- **Dynamic degree-based sampling**, which samples nodes according to their current degrees and avoids redundant computations.
- **Surplus-degree rewiring**, which improves local clustering while preserving the intended degree characteristics.

Compared with recent Chung–Lu-based generation methods, FastGraph reduces the computational complexity from $O(n^3)$ to $O(n^2)$. In the experiments reported in the paper, it achieves an average runtime reduction of nearly **12×** when generating graphs with the same number of nodes and similar numbers of edges. FastGraph can reproduce the structural properties of more than a dozen real-world social networks and generate graphs at arbitrary scales.

## Repository Contents

| File | Description |
| --- | --- |
| `FastGraph.py` | Generates directed social network graphs with reciprocal edges and high clustering. |
| `Analysis.py` | Computes 17 topological metrics for generated or real-world networks. |
| `SIR.py` | Runs a basic discrete-time susceptible–infected–recovered (SIR) simulation. |
| `Hyperparameters.docx` | Describes the input parameters and their settings. |

## Requirements

The code was developed with **Python 3.8.5** and requires the following packages:

- NumPy
- pandas
- Matplotlib
- NetworkX
- SciPy
- EoN

The Python `datetime` module is part of the standard library and does not need to be installed separately.

### Installation with Conda

```bash
conda create -n fastgraph python=3.8.5
conda activate fastgraph
conda install numpy pandas matplotlib networkx scipy
pip install EoN
```

## Usage

Before running the code, consult `Hyperparameters.docx` and configure the required input parameters.

### Generate a graph

```bash
python FastGraph.py
```

### Analyze topological properties

```bash
python Analysis.py
```

### Run an SIR simulation

```bash
python SIR.py
```

## Citation

If you use FastGraph in your research, please cite:

> Q. Li, R. Liu, R. Chen, and T. Song, “FastGraph: Fast Large-Scale Directed Social Network Graph Generation,” *IEEE Transactions on Computational Social Systems*, 2025.

```bibtex
@article{li2025fastgraph,
  author  = {Li, Q. and Liu, R. and Chen, R. and Song, T.},
  title   = {FastGraph: Fast Large-Scale Directed Social Network Graph Generation},
  journal = {IEEE Transactions on Computational Social Systems},
  year    = {2025}
}
```

## License

Please refer to the repository's license file for the applicable terms of use. If the repository does not yet include a license, add one before distributing or reusing the code.

## Contact

For questions, bug reports, or suggestions, please open an issue in this repository.
