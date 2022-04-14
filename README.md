## HE-Booster: An Efficient Polynomial Arithmetic Acceleration on GPUs for Homomorphic Encryption
HE-Booster is a GPU-accelerated polynomial arithmetic library for homomorphic encryption. 
HE-Booster can significantly boost performance while providing an easy-to-use interface that greatly improves programmer productivity. 
It utilizes two popular parallel algorithms (e.g., CRT and NTT) to exploit thread-level parallelism and makes full use of GPU hardware features (e.g., unified virtual memory and asynchronous copy) to further improve performance. 

## Hardware Requirements
1. NVIDIA [CUDA-Enabled GPUs](https://developer.nvidia.com/cuda-gpus) with computation compability 8.6. Specially, NVIDIA GPU card with Ampere architecture is required, such as GeForce RTX3070, 3080, etc.
2. The NVIDIA CUDA driver version 460.32.03.

## Install
1. **Download the container file**
  Link this address ---> [hebooster.tar](https://drive.google.com/file/d/1h39QwieUE6qrg6uAJVX8N2zoAgwwllmw/view?usp=sharing)
  
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
1. Enter into folder: `cd /root/BGV_on_GPU/Schemes/BGV_NWC64`.
2. Execute the command: `./FHE_BGV_Performance_test 8192`. Other two parameters 16384 and 32768 can be used to replace 8192.

## Experimental Results
**1. Perform the first parameter set: `./FHE_BGV_Performance_test 8192`**

Part 1: CRT and NTT

================================================================= CRT kernel time is 6.90483 microseconds
=================================================================ICRT kernel time is 25.4956 microseconds
================================================================= NTT kernel time is 12.544 microseconds
=================================================================INTT kernel time is 12.7222 microseconds

Part 2: Encryption and Decryption

=================================================================Enc time is 187.392 microseconds
=================================================================Dec time is 148.48 microseconds

Part 3: Homomorphic Addition

=================================================================Homomorphic Add time is 3.67616 microseconds

Part 4: Homomorphic Multiplication

=================================================================Homomorphic Mul time is 4.84864 microseconds

Part 5: Key Switching

=================================================================Key Switching time is 362.291 microseconds

**2. Perform the second parameter set: `./FHE_BGV_Performance_test 16384`**

Part 1: CRT and NTT

================================================================= CRT kernel time is 19.1508 microseconds
=================================================================ICRT kernel time is 72.5514 microseconds
================================================================= NTT kernel time is 13.0734 microseconds
=================================================================INTT kernel time is 13.2833 microseconds

Part 2: Encryption and Decryption

=================================================================Enc time is 338.624 microseconds
=================================================================Dec time is 230.18 microseconds

Part 3: Homomorphic Addition

=================================================================Homomorphic Add time is 18.00019 microseconds

Part 4: Homomorphic Multiplication

=================================================================Homomorphic Mul time is 23.84864 microseconds

Part 5: Key Switching

=================================================================Key Switching time is 992.291 microseconds

**3. Perform the third parameter set: `./FHE_BGV_Performance_test 32768`**

Part 1: CRT and NTT

================================================================= CRT kernel time is 149.537 microseconds
=================================================================ICRT kernel time is 394.464 microseconds
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

=================================================================Key Switching time is 3240.291 microseconds


