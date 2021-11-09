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
