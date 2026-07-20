# **small as s##t linux**

My first (and bad) attempt at making the lightest linux distro possible.

Runs at a minimum of ***78M*** of RAM.

## **Build and run:**

### 0. Make sure you have QEMU installed

### 1. Clone the repo

```bash
git clone https://github.com/coppergaming85/small-as-shit-linux && cd small-as-shit-linux
```

### 2. Download and extract Linux (version I used is 7.0.9)

```bash
wget -O - https://www.kernel.org/pub/linux/kernel/v7.x/linux-7.0.9.tar.xz | tar -xJ
```

### 3. Copy `linux-kernel.config` to the `linux-7.0.9` directory as `.config`

```bash
cp ./linux-kernel.config ./linux-7.0.9/.config
```

### 4. Build the kernel

```bash
cd linux-7.0.9 && make -j$(nproc) && cd ..
```

### 5. And the initramfs/initrd

```bash
chmod +x ./build-initrd && ./build-initrd
```

### 6. Launch with script

```bash
chmod +x ./launch && ./launch
```

#

### This project includes the source code and binaries of `fastfetch` and `busybox`, licensed under the MIT and GPLv2 licenses, respectively.

### See `LICENSE-fastfetch` and `LICENSE-busybox` for details.
