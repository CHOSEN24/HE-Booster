## HE-Booster: An Efficient Polynomial Arithmetic Acceleration on GPUs for Homomorphic Encryption
HE-Booster is a GPU-accelerated polynomial arithmetic library for homomorphic encryption. HE-Booster can significantly boost performance while providing an easy-to-use interface that greatly improves programmer productivity. It utilizes parallel algorithms (e.g., CRT and NTT) to exploit thread-level parallelism, and makes full use of GPU hardware features (e.g., unified virtual memory and asynchronous copy) to further improve performance. 

## Hardware Requirements
1. NVIDIA [CUDA-Enabled GPUs](https://developer.nvidia.com/cuda-gpus) with computation compability 8.6. Specially, NVIDIA GPU card with Ampere architecture is required, such as GeForce RTX3070, 3080, etc.
2. The NVIDIA CUDA Driver version 460.32.03.

## Install
1. **Download the container file**
  Link this address ---> [hebooster.tar](https://drive.google.com/file/d/1h39QwieUE6qrg6uAJVX8N2zoAgwwllmw/view?usp=sharing)
  
2. **Unzip the file**
   ```
   unzip hebooster.tar.zip
   ```
   
3. **Load the container**
   ```
   docker load < hebooster.tar
   ```
   
4. **Find `hebooster` image ID and run it**
   ```
   docker run -itd --rm --name hebooster --gpus all <Image ID>
   ```
   
5. **Enter into the `hebooster` conrainer**
   ```
   docker attach <container ID>
   ```

## Execution
1. Enter into folder: `cd /root/BGV_on_GPU/Schemes/BGV_NWC64`.
2. Execute the command: `./FHE_BGV_Performance_test 8192`. Other two parameters 16384 and 32768 can be used to replace 8192.
