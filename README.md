## HE-Booster: An Efficient Polynomial Arithmetic Acceleration on GPUs for Homomorphic Encryption
---
HE-Booster is a GPU-accelerated polynomial arithmetic library for homomorphic encryption. HE-Booster can significantly boost performance while providing an easy-to-use interface that greatly improves programmer productivity. It utilizes parallel algorithms (e.g., CRT and NTT) to exploit thread-level parallelism, and makes full use of GPU hardware features (e.g., unified virtual memory and asynchronous copy) to further improve performance. 

## Hardware Requirements
1. NVIDIA [CUDA-Enabled GPUs](https://developer.nvidia.com/cuda-gpus) with computation compability 8.6. Specially, NVIDIA GPU card with Ampere architecture is required, such as GeForce RTX3070, 3080, etc.
2. The NVIDIA CUDA Driver version 460.32.03.

## Installing
1. Download the container file. 
  Linked this address. [hebooster.tar]<https://drive.google.com/file/d/1h39QwieUE6qrg6uAJVX8N2zoAgwwllmw/view?usp=sharing>
3. Unzip the file
  unzip hebooster.tar.zip
