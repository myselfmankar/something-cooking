# Scalable Friend Recommendation using Node2Vec and Annoy

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

A scalable friend recommendation system using Node2Vec embeddings and Annoy, demonstrating a >450,000x speedup over a traditional MLP-based link prediction approach. This repository contains the code and experiments for the paper "Friend Recommendation using Graph Embeddings for Social Media."

## About The Project

Friend recommendation is a critical but computationally expensive task in large-scale social networks. This project explores and compares two methods for link prediction:

1.  **A Brute-Force Supervised Method:** Uses Node2Vec embeddings with a Multilayer Perceptron (MLP) to predict the probability of a link between every non-connected pair of users. While accurate, this method is too slow for real-time applications.
2.  **An Optimized ANN-Based Method:** Uses the same Node2Vec embeddings but leverages **Annoy (Approximate Nearest Neighbors Oh Yeah)** to build an index for ultra-fast similarity search. This method serves as a highly efficient proxy for the supervised model.

The key finding is a **>450,000x performance improvement** with the Annoy-based approach, making it suitable for real-time recommendation systems.

### Built With

*   [Python](https://www.python.org/)
*   [Jupyter Notebook](https://jupyter.org/)
*   [NetworkX](https://networkx.org/)
*   [Node2Vec](https://github.com/eliorc/node2vec)
*   [Annoy](https://github.com/spotify/annoy)
*   [TensorFlow/Keras](https://www.tensorflow.org/)
*   [Pandas](https://pandas.pydata.org/)
*   [Scikit-learn](https://scikit-learn.org/)

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

You will need Python 3.x and pip installed on your system.

### Installation

1.  Clone the repo:
    ```sh
    git clone https://github.com/your-username/scalable-friend-recommendation.git
    cd scalable-friend-recommendation
    ```
2.  Install the required Python packages. A `requirements.txt` file is included for convenience.
    ```sh
    pip install -r requirements.txt
    ```

## Usage

The entire workflow is contained within the `stcf_finalnb_draft.ipynb` Jupyter Notebook.

1.  **Download the Dataset:** The notebook includes a command to download the SNAP Facebook dataset. Make sure you run this cell first.
    ```sh
    !wget http://snap.stanford.edu/data/facebook.tar.gz
    !tar -xvf "facebook.tar.gz"
    ```
2.  **Run the Notebook:** Open the notebook in Jupyter or Google Colab and execute the cells in order. The notebook will:
    *   Construct the graph.
    *   Generate Node2Vec embeddings.
    *   Train the MLP for link prediction.
    *   Build the Annoy index.
    *   Run and time both the brute-force and optimized recommendation methods.

## Results

The experiments highlight two key outcomes: the high accuracy of the link prediction model and the dramatic speedup from using Annoy.

#### Link Prediction Performance

The MLP classifier achieved an overall accuracy of **95%** on the held-out test set.

| Metric | Class 0 (No Link) | Class 1 (Link) |
| :--- | :---: | :---: |
| Precision | 0.94 | 0.95 |
| Recall | 0.95 | 0.94 |
| F1-Score | 0.95 | 0.95 |

#### Recommendation Method Performance Comparison

The optimized ANN-based method is over **450,000 times faster** than the brute-force MLP approach.

| Recommendation Method | Execution Time (seconds) |
| :--- | :---: |
| Brute Force (MLP) | 91.3630 |
| **Optimized (ANN-based)** | **0.0002** |

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

Vaishnav Mankar - vaishnav.mankar04@gmail.com

Project Link: [https://github.com/your-username/scalable-friend-recommendation](https://github.com/your-username/scalable-friend-recommendation)

## How to Cite

If you use this work in your research, please cite the following paper:

```bibtex
@article{mankar2024friend,
  title={Friend Recommendation using Graph Embeddings for Social Media},
  author={Mankar, Vaishnav},
  journal={arXiv preprint},
  year={2024}
}
