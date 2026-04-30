# Linux'ta Ekran Kartı Sürücüsü İndirme Rehberi

Linux'ta ekran kartı sürücüsü konusunda sorun yaşayan kişiler için, GPU kurulum rehberi. Eğer kullandığınız GPU, AMD Radeon veya Intel Arc ise bu rehberi okumanıza gerek yok, yapmanız gereken bir şey yok, ihtiyacınız olan şeyler zaten kernelde gömülü.

## Nvidia Driverları Nasıl Yüklenir?

CachyOS, NyarchLinux gibi dağıtımlarda hazır yüklü geliyor olsa da Nvidia driverlarını yüklemek bazı kullanıcılar için karışık geliyor olabilir. Bu adımda ne yapmanız gerektiğini anlatacağım.

### Arch Linux (ve Arch tabanlı dağıtım) kullanıcıları:
```bash
sudo pacman -S nvidia-open
```
Ardından sistemi yeniden başlatın. Eğer laptop kullanıyorsanız `nvidia-open` 'a ek olarak `nvidia-prime` da indirmelisiniz. Laptop kullanıyorsanız arch tabanlı bir dağıtım kullanmanız en iyisi olacaktır.

### Fedora tabanlı dağıtım kullanıcıları
```bash
sudo dnf config-manager addrepo --from-repofile=https://developer.download.nvidia.com/compute/cuda/repos/fedora43/x86_64/cuda-fedora43.repo
sudo dnf clean expire-cache
```

Açık kaynaklı sürücüleri istiyorsanız
```bash
sudo dnf install nvidia-open
```

Kapalı kaynaklı sürücüleri istiyorsanız
```bash
sudo dnf install cuda-drivers
```

Ayrıca laptop için:
```bash
cat << 'EOF' | sudo tee /usr/bin/prime-run > /dev/null
#!/bin/bash
__NV_PRIME_RENDER_OFFLOAD=1 __VK_LAYER_NV_optimus=NVIDIA_only __GLX_VENDOR_LIBRARY_NAME=nvidia "$@"
EOF

sudo chmod +x /usr/bin/prime-run
```

ardından sistemi yeniden başlatın

### Ubuntu tabanlı dağıtım kullanıcıları

```bash
sudo apt install nvidia-drivers-595
```
Ayrıca laptop için:
```bash
cat << 'EOF' | sudo tee /usr/bin/prime-run > /dev/null
#!/bin/bash
__NV_PRIME_RENDER_OFFLOAD=1 __VK_LAYER_NV_optimus=NVIDIA_only __GLX_VENDOR_LIBRARY_NAME=nvidia "$@"
EOF
```
ardından sistemi yeniden başlatın

## AMDGPU Kullanıcıları
Arch Linux için `vulkan-radeon` pakedini indirebilirsiniz. Başka bir şey yapmanıza gerek yok 

## Intel Arc Kullanıcıları
Arch Linux için `vulkan-intel` pakedini indirebilirsiniz. Başka bir şey yapmanıza gerek yok 
