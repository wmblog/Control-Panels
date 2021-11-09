# Ubuntu 20.04 üzerine HestiaCP kurulumu

## Kuruluma hazırlık

### Ubuntu root şifresini değiştirme
```bash
sudo passwd
```
### Güncelleme kontrolü
```bash
sudo apt-get update -y && apt-get upgrade -y
sudo apt-get autoremove --purge
```
### Swap oluşturma

```bash
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
sudo cp /etc/fstab /etc/fstab.orj
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
sudo cp /etc/sysctl.conf /etc/sysctl.conf.orj
echo 'vm.swappiness=10' | sudo tee -a /etc/sysctl.conf
echo 'vm.vfs_cache_pressure=50' | sudo tee -a /etc/sysctl.conf
```
