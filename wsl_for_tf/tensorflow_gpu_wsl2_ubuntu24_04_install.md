
# Install TensorFlow GPU on WSL2 Ubuntu 24.04 (Windows 11)  
**CUDA 11.8 + cuDNN 8.6 + TensorFlow 2.12.0**

---

## 1. System Update & Build Tools

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential
```

---

## 2. Install Miniconda (Optional but Recommended)

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash ./Miniconda3-latest-Linux-x86_64.sh
# Follow installer instructions
```

---

## 3. Install CUDA 11.8

```wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run
sudo sh cuda_11.8.0_520.61.05_linux.run
```

Make sure CUDA 11.8 is installed. Set environment variables in `~/.bashrc`:

```bash
export PATH=/usr/local/cuda-11.8/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-11.8/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```

Apply the changes:

```bash
source ~/.bashrc
```

Verify CUDA installation:

```bash
nvcc --version
```

---

## 4. Install cuDNN 8.6 for CUDA 11.8

Download cuDNN 8.6 archive compatible with CUDA 11 from [NVIDIA cuDNN archive](https://developer.nvidia.com/rdp/cudnn-archive).

Extract and copy files:

```bash
tar -xvf cudnn-linux-x86_64-8.6.0.163_cuda11-archive.tar.xz
cd cudnn-linux-x86_64-8.6.0.163_cuda11-archive

sudo cp include/cudnn*.h /usr/local/cuda-11.8/include/
sudo cp lib/libcudnn* /usr/local/cuda-11.8/lib64/

sudo chmod a+r /usr/local/cuda-11.8/include/cudnn*.h /usr/local/cuda-11.8/lib64/libcudnn*
```

Check files:

```bash
ls -l /usr/local/cuda-11.8/lib64/libcudnn*
ls -l /usr/local/cuda-11.8/include/cudnn*.h
```

---

## 5. Update linker cache

Add CUDA library path to the linker configuration:

```bash
echo "/usr/local/cuda-11.8/lib64" | sudo tee /etc/ld.so.conf.d/cuda.conf
sudo ldconfig
```

---

## 6. Verify cuDNN installation (Optional test)

Create a test file `test_cudnn.c` with the following content:

```c
#include <cudnn.h>
#include <stdio.h>

int main() {
    cudnnHandle_t handle;
    cudnnStatus_t status = cudnnCreate(&handle);
    if (status == CUDNN_STATUS_SUCCESS) {
        printf("cuDNN successfully initialized.\n");
    } else {
        printf("cuDNN initialization failed.\n");
    }
    cudnnDestroy(handle);
    return 0;
}
```

Compile and run:

```bash
gcc -o test_cudnn test_cudnn.c -I/usr/local/cuda-11.8/include -L/usr/local/cuda-11.8/lib64 -lcudnn
./test_cudnn
```

Expected output:

```
cuDNN successfully initialized.
```

---

## 7. Install TensorFlow 2.12 with GPU support in Conda environment

Create and activate conda environment:

```bash
conda create -n tf_gpu python=3.10 -y
conda activate tf_gpu
```

Install TensorFlow:

```bash
pip install tensorflow==2.12.0
```

---

## 8. Verify TensorFlow GPU access

Run Python:

```python
import tensorflow as tf
print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
```

Expected output:

```
Num GPUs Available: 1
```

---

## Notes:

- You can install multiple CUDA versions side-by-side, but only one version is active at a time, controlled by environment variables.
- Make sure your NVIDIA driver supports your CUDA version.
- Always update `~/.bashrc` accordingly when switching CUDA versions.

---

*This documentation is based on an installation on WSL2 Ubuntu 24.04 with CUDA 11.8 and cuDNN 8.6.*
