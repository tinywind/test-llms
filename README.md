## CUDA toolkit download & install
- https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local
   - wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
   - sudo mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600
   - wget https://developer.download.nvidia.com/compute/cuda/12.3.2/local_installers/cuda-repo-wsl-ubuntu-12-3-local_12.3.2-1_amd64.deb
   - sudo dpkg -i cuda-repo-wsl-ubuntu-12-3-local_12.3.2-1_amd64.deb
   - sudo cp /var/cuda-repo-wsl-ubuntu-12-3-local/cuda-*-keyring.gpg /usr/share/keyrings/
   - sudo apt-get update
   - sudo apt-get -y install cuda-toolkit-12-3

## SWAP 공간 설정: 물리 메모리 공간이 부족하다면 다음과 같이 설정

1. 현재 스왑 설정 확인: `sudo swapon --show`
2. 스왑 파일 생성
```
    sudo fallocate -l 128G /swapfile
    sudo chmod 600 /swapfile
    sudo mkswap /swapfile
    sudo swapon /swapfile
```
3. 영구적 스왑 설정: `echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab`