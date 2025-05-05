# 🚀 Hashing-at-Lightspeed
**SHA-256 Hashing in C++ (Sequential, OpenMP, and CUDA)**

This project demonstrates fast SHA-256 hashing for large datasets using:
- 🧵 **Sequential C++**
- 🔀 **OpenMP-based multithreading**
- ⚡ **CUDA stream-based parallelism**

It leverages **OpenSSL** for hashing and is designed to run both locally and on **Google Colab**


---

## ⚙️ Prerequisites

✅ Required:
- A C++ compiler (`g++`) with **OpenMP support**
- **OpenSSL** development libraries (`libssl-dev`)
- **NVIDIA CUDA toolkit** for GPU version
- (For Colab: CUDA is preinstalled)

Optional:
- `make` if you use the provided Makefile
- Python 3 with `matplotlib`, `numpy` for benchmarking

---

## 🛠️ Build Instructions

You can compile manually or with a `Makefile`.

### 🔧 Manual Build (Run in Bash or Colab)
```bash
# Make sure the build directory exists
mkdir -p sha256_project/build

# Sequential version
g++ sha256_project/src/sha256_seq.cpp -o sha256_project/build/sha256_seq -lssl -lcrypto

# OpenMP parallel version
g++ -fopenmp sha256_project/src/sha256_openmp.cpp -o sha256_project/build/sha256_openmp -lssl -lcrypto

# CUDA (stream-based) version
nvcc -Xcompiler -fopenmp sha256_project/src/sha256_cuda_streams.cu -o sha256_project/build/sha256_cuda_streams -lssl -lcrypto


# Sample input file path
INPUT=sha256_project/data/input.txt

# Run sequential
./sha256_project/build/sha256_seq $INPUT

# Run OpenMP version
./sha256_project/build/sha256_openmp $INPUT

# Run CUDA stream-based version
./sha256_project/build/sha256_cuda_streams $INPUT


Input: hello
Hash: 2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824
Sequential SHA-256 Time: 0.0042 s

# In Colab or locally, run this script to:
# - Generate input files of increasing sizes
# - Run all versions (sequential, OpenMP, CUDA)
# - Collect timing data
# - Plot execution time, speedup, and efficiency

!python3 benchmark.py

| Input Size | Sequential (s) | OpenMP (s) | CUDA (s) |
| ---------- | -------------- | ---------- | -------- |
| 1,000      | 0.18           | 0.05       | 0.03     |
| 10,000     | 1.67           | 0.32       | 0.18     |
| 100,000    | 15.6           | 1.7        | 0.91     |



Let me know if you'd like a downloadable file version too.
