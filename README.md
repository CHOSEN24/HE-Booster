## HE-Booster: An Efficient Polynomial Arithmetic Acceleration on GPUs for Homomorphic Encryption
HE-Booster is a GPU-accelerated polynomial arithmetic library for homomorphic encryption. 
HE-Booster can significantly boost performance while providing an easy-to-use interface that greatly improves programmer productivity. 
It utilizes two popular parallel algorithms (e.g., CRT and NTT) to exploit thread-level parallelism and makes full use of GPU hardware features (e.g., unified virtual memory and asynchronous copy) to further improve performance. 

**Note that in addition to the experiments in the original submission, we supplement the revised submission with new contributions, mainly including the performance evaluation of _modulus switching_ and _automorphism_. In addition, we propose a multi-GPU acceleration design and evaluate the performance boost of homomorphic multiplication (HEMUL).**

## Software/Hardware Requirements
1. NVIDIA [CUDA-Enabled GPUs](https://developer.nvidia.com/cuda-gpus) with computation compability 8.6. Specially, NVIDIA GPU card with Ampere architecture is required, such as GeForce RTX3070, etc.
2. The NVIDIA CUDA driver version 460.32.03.
3. The NVIDIA CUDA Toolkit version 11.2.

## Install
1. **Download the container file [HE-Booster link](https://drive.google.com/file/d/1h39QwieUE6qrg6uAJVX8N2zoAgwwllmw/view).**
  
2. **Unzip the file**
   ```
   unzip hebooster.tar.zip
   ```
   
3. **Import the Image**
   ```
   docker load < hebooster.tar
   ```
   
4. **Find `hebooster` image ID and run it**
   ```
   docker run -itd --rm --name hebooster --gpus all <Image ID>
   ```
   
5. **Enter into the `hebooster` container**
   ```
   docker attach <container ID>
   ```

## Execution
1. Enter into folder: `cd /root/BGV_on_GPU_Revised/Schemes/BGV_NWC64`.
2. Execute the command: `./FHE_BGV_Performance_test 8192`. Other two parameters 16384 and 32768 can be employed.

## Experimental Results
**Note: Parts 1-5 are the experimental results of the original submission, while Parts 6-7 are the experimental results of the revised submission, including the performance of _Modulus Switching_ and _Automorphism_.**

**1. Perform the first parameter set: `./FHE_BGV_Performance_test 8192`**

Part 1: CRT and NTT

================================================================= CRT kernel time is 13.90483 microseconds

=================================================================ICRT kernel time is 26.4956 microseconds

================================================================= NTT kernel time is 12.544 microseconds

=================================================================INTT kernel time is 12.7222 microseconds

Part 2: Encryption and Decryption

=================================================================Enc time is 187.392 microseconds

=================================================================Dec time is 148.48 microseconds

Part 3: Homomorphic Addition

=================================================================Homomorphic Add time is 6.67616 microseconds

Part 4: Homomorphic Multiplication

=================================================================Homomorphic Mul time is 6.84864 microseconds

Part 5: Key Switching

=================================================================Key Switching time is 462.291 microseconds

Part 6: Modulus Switching

=================================================================Modulus Switching time is 5.291 microseconds

Part 7: Automorphism

=================================================================Automorphism time is 7.233 microseconds

---

**2. Perform the second parameter set: `./FHE_BGV_Performance_test 16384`**

Part 1: CRT and NTT

================================================================= CRT kernel time is 44.1508 microseconds

=================================================================ICRT kernel time is 72.5514 microseconds

================================================================= NTT kernel time is 13.0734 microseconds

=================================================================INTT kernel time is 13.2833 microseconds

Part 2: Encryption and Decryption

=================================================================Enc time is 338.624 microseconds

=================================================================Dec time is 230.18 microseconds

Part 3: Homomorphic Addition

=================================================================Homomorphic Add time is 22.00019 microseconds

Part 4: Homomorphic Multiplication

=================================================================Homomorphic Mul time is 23.84864 microseconds

Part 5: Key Switching

=================================================================Key Switching time is 872.291 microseconds

Part 6: Modulus Switching

=================================================================Modulus Switching time is 8.362 microseconds

Part 7: Automorphism

=================================================================Automorphism time is 15.739 microseconds

---

**3. Perform the third parameter set: `./FHE_BGV_Performance_test 32768`**

Part 1: CRT and NTT

================================================================= CRT kernel time is 222.537 microseconds

=================================================================ICRT kernel time is 385.464 microseconds

================================================================= NTT kernel time is 17.6681 microseconds

=================================================================INTT kernel time is 18.6429 microseconds

Part 2: Encryption and Decryption

=================================================================Enc time is 796.25 microseconds

=================================================================Dec time is 333.18 microseconds

Part 3: Homomorphic Addition

=================================================================Homomorphic Add time is 70.00019 microseconds

Part 4: Homomorphic Multiplication

=================================================================Homomorphic Mul time is 87.84864 microseconds

Part 5: Key Switching

=================================================================Key Switching time is 2360.291 microseconds

Part 6: Modulus Switching

=================================================================Modulus Switching time is 22.198 microseconds

Part 7: Automorphism

=================================================================Automorphism time is 54.410 microseconds


