### Ubuntu 22.04.3 LTS
```shell



python --version
apt install build-essential software-properties-common zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev -y
apt install wget nvtop python-is-python3 aria2 unrar -y

lsmod | grep nouveau
cat <<EOF | sudo tee /etc/modprobe.d/blacklist-nouveau.conf
blacklist nouveau
options nouveau modeset=0
EOF
sudo update-initramfs -u
sudo reboot
nvidia-smi
nano /etc/ld.so.conf
ldconfig

nano .bashrc
ldconfig
nvcc --version

wget https://developer.download.nvidia.com/compute/cuda/12.1.0/local_installers/cuda_12.1.0_530.30.02_linux.run
sudo sh cuda_12.1.0_530.30.02_linux.run
```

### Jupyter

```shell
sudo systemctl daemon-reload
sudo systemctl start jupyter-lab
sudo systemctl enable jupyter-lab
```

If every person gets 24 hours of compute time every week with a 3090 or A5000 GPU 7 people can use it. with 2xGPU 14 people, with 24xGPU 168 people ...

# First Server Parts

### GPU: 2 x Nvidia A5000 (2-slot 24GB) or 3090 Turbo (2-slot 24GB)
https://www.nvidia.com/en-us/design-visualization/rtx-a5000 <br />
https://www.techpowerup.com/gpu-specs/gigabyte-rtx-3090-turbo.b8061 <br />

### Motherboard: Pro WS C621-64L SAGE (4 GPU Support)
https://www.asus.com/Commercial-Servers-Workstations/Pro-WS-C621-64L-SAGE/

### CPU: Intel® Xeon® W-3235 Processor (64 Lane PCIe 3.0) (4 GPU Support)
https://www.intel.com/content/www/us/en/products/sku/193749/intel-xeon-w3235-processor-19-25m-cache-3-30-ghz/specifications.html

### Ram: 384GB (32GBx12) DDR4 1rx4 2933MHz or 3200MHz 

### Power supply: 1600 Watt 80+ TITANIUM

### Case: E-ATX

# How will we pay the electricity cost and collect money for more GPUs?
Electricity cost: 1xGPU 3090 or A5000 24 Hours $2
