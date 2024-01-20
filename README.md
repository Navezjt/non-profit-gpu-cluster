🐣 Please follow me for new updates https://twitter.com/camenduru <br />
🔥 Please join our discord server https://discord.gg/k5BwmmvJJU <br />
🥳 Please join my patreon community https://patreon.com/camenduru <br />

## SSH root login
```shell
sudo nano /etc/ssh/sshd_config
PermitRootLogin prohibit-password to PermitRootLogin yes
sudo systemctl restart ssh
sudo passwd
sudo ufw allow ssh
```

### Ubuntu 22.04.3 LTS
```shell
apt install build-essential software-properties-common zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev -y
apt install wget nvtop python-is-python3 aria2 unrar -y
```

### Cuda 12.1.0_530.30.02
```shell
lsmod | grep nouveau
cat <<EOF | sudo tee /etc/modprobe.d/blacklist-nouveau.conf
blacklist nouveau
options nouveau modeset=0
EOF
sudo update-initramfs -u
sudo reboot

wget https://developer.download.nvidia.com/compute/cuda/12.1.0/local_installers/cuda_12.1.0_530.30.02_linux.run
sh cuda_12.1.0_530.30.02_linux.run
nvidia-smi
nano /etc/ld.so.conf
ldconfig

nano .bashrc
ldconfig
nvcc --version
```

### Python 3.10.12
```shell

pip install torch==2.1.0+cu121 torchvision==0.16.0+cu121 torchaudio==2.1.0+cu121 torchtext==0.16.0 torchdata==0.7.0 --extra-index-url https://download.pytorch.org/whl/cu121
pip install notebook
pip show torch notebook
```

### Jupyter

```shell
systemctl daemon-reload
systemctl start jupyter-lab
systemctl enable jupyter-lab
systemctl list-unit-files --type=service --state=enabled
```

If every person gets 24 hours of compute time every week with a 3090 or A5000 GPU 7 people can use it. with 2xGPU 14 people, with 24xGPU 168 people ... <br />
Operation cost (electricity): 2xGPU 3090 or A5000 24 Hours ~$2 <br />
End-of-the-year goal: 6 servers with a total of 24 x A5000 or 3090 GPUs. <br />

# First Prototype Server Parts:

- GPU1: Asus ROG Strix RTX3090 O24G (3-slot 24GB with Liquid Cooler 2-slot)
- GPU2: Nvidia A5000 (2-slot 24GB) or 3090 Turbo (2-slot 24GB)
- Motherboard: Pro WS C621-64L SAGE (4 GPU Support)
- CPU: Intel® Xeon® W-3235 Processor (64 Lane PCIe 3.0) (4 GPU Support)
- Ram: 384GB (32GBx12) DDR4 1rx4 2933MHz or 3200MHz
- SSD: 4TB
- Power supply: Corsair AX1500i 1500 Watt 80+ Titanium
- Case: Antec P20C-W (E-ATX)
- Operation cost (electricity): 2xGPU 3090 or A5000 24 Hours ~$2


# Updates:

### January 20 2024
![mb_one_ram_case](https://github.com/camenduru/Community-GPU-Cluster/assets/54370274/805fdf46-4fee-46d3-a41b-b827d959e860)