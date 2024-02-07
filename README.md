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
