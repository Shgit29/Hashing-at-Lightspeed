# Hashing-at-Lightspeed

# SHA-256 Hashing in C++ (Sequential vs. Parallel with OpenMP)

This project demonstrates how to compute SHA-256 hashes for a list of strings using both **sequential** and **parallel** approaches in C++. It uses the OpenSSL library for hashing and OpenMP for parallelization.

## ⚙️ Prerequisites

- A C++ compiler with OpenMP support (`g++`, `clang++`, etc.)
- OpenSSL development libraries
- Make (optional, if you use a Makefile)

## 🛠️ Build Instructions

To compile both versions:

```bash
# Sequential version
g++ src/sha256_seq.cpp -o sha256_seq -lssl -lcrypto

# Parallel version with OpenMP
g++ src/sha256_openmp.cpp -o sha256_openmp -fopenmp -lssl -lcrypto

# Run sequential version
./sha256_seq

# Run parallel version
./sha256_openmp

#Sample Output
Input: hello
Hash: 2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824

Sequential SHA-256 Time: 0.0042 s
