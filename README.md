# Scalable Friend Recommendation using Node2Vec and Annoy

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

A scalable friend recommendation system using Node2Vec embeddings and Annoy, demonstrating a >450,000x speedup over a traditional MLP-based link prediction approach. This repository contains the code and experiments for the paper "Friend Recommendation using Graph Embeddings for Social Media."

## About The Project

Friend recommendation is a critical but computationally expensive task in large-scale social networks. This project explores and compares two methods for link prediction:

1.  **A Brute-Force Supervised Method:** Uses Node2Vec embeddings with a Multilayer Perceptron (MLP) to predict the probability of a link between every non-connected pair of users. While accurate, this method is too slow for real-time applications.
2.  **An Optimized ANN-Based Method:** Uses the same Node2Vec embeddings but leverages **Annoy (Approximate Nearest Neighbors Oh Yeah)** to build an index for ultra-fast similarity search. This method serves as a highly efficient proxy for the supervised model.

The key finding is a **>450,000x performance improvement** with the Annoy-based approach, making it suitable for real-time recommendation systems.
## How to Cite

If you use this work in your research, please cite the following paper:
[V Mankar](https://github.com/myselfmankar)
