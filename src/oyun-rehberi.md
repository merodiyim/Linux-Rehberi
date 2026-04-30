# Linux'ta Oyun Rehberi \[Not: Bu Rehber Geliştirme Aşamasındadır]

Linux, son 4 yılda oyun konusunda epey ilerledi ve TechPowerUp'ın verilerine göre Steam'deki her 10 oyundan 9 tanesini yürütebiliyor. Bu rehberin yazıldığı 30.04.2026 itibariyle Linux 7.0 kerneli yayınlandı ve bu da pek çok donanım için epey iyi bir şey.

Rehberimizin konusu olan Linux'ta oyun oynamaya değinelim. 3 başlık ile ele alacağız steam oyunları, epic games oyunları ve diğer oyunlar

## Steam Oyunları
Hemen hemen her Steam oyunu Linux'ta açtığınız gibi çalışacaktır. Ek bir ayar yapmanıza gerek kalmıyor

### Steam Nasıl İndirilir?
Arch Linux tabanlı dağıtımlar için şu adımları takip edin:
```bash
sudo pacman -S steam
```

Fedora tabanlı dağıtımlar için şu adımları takip edin; (Non-Free repoların aktif olduğundan emin olun)
```bash
sudo dnf install steam
```

Debian/Ubuntu tabanlı dağıtımlar için Steam'in kendi sitesinden yükle butonuna bastığınızda gelen .deb dosyasını yürütün

### Epic Games Oyunları
Epic Games oyunlarınız için Heroic Games Launcher indirmelisiniz. 
https://heroicgameslauncher.com/
