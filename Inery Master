# Inery-master

<p align="center">
  <img height="50" height="auto" src="https://user-images.githubusercontent.com/38981255/184088981-3f7376ae-7039-4915-98f5-16c3637ccea3.PNG">
</p>

# Tutorial Become a Master Node

**Dokumen Official :**
> [Node Lite & Master](https://docs.inery.io/docs/category/lite--master-nodes)

**Explorer :**
> [Explorer Inary](https://explorer.inery.io/ "Explorer Inary")

## Perangkat Keras

|  Komponen |  Persyaratan Minimum |
| ------------ | ------------ |
| CPU  | Intel Core i7-8700 Hexa-Core  |
| RAM | DDR4 64 GB  |
| Penyimpanan  | 2x1 TB NVMe SSD |
| koneksi | Port 1 Gbit/dtk |

## Perangkat Lunak

|Komponen | Persyaratan Minimum |
| ------------ | ------------ |
| OS |  Ubuntu 18.04 atau lebih tinggi | 


## 1. Update Tools Yang di Perlukan
```
sudo apt-get update && sudo apt install git && sudo apt install screen
```
```
sudo apt-get install -y make bzip2 automake libbz2-dev libssl-dev doxygen graphviz libgmp3-dev \
autotools-dev libicu-dev python2.7 python2.7-dev python3 python3-dev \
autoconf libtool curl zlib1g-dev sudo ruby libusb-1.0-0-dev \
libcurl4-gnutls-dev pkg-config patch llvm-7-dev clang-7 vim-common jq libncurses5
```
## 2. On Port
```
ufw allow 22 && ufw allow 8888 && ufw allow 9010 && ufw enable
```
untuk azure kalian bisa open port langsung di portal
## 3. Mulai Node
```
git clone https://github.com/inery-blockchain/inery-node
```
## 4. Explorer BIN
```
cd inery-node
```
## 5. Beri Izin File
```
cd inery.setup
```
```
chmod +x ine.py
```
```
./ine.py --export
```
```
cd; source .bashrc; cd -
```
## 6. Become a Master Node
untuk mengonfigurasi node dengan informasi IP server Anda, buka `inery-node/inery.setup/tools/` buka `config.json`
```
cd ~/inery-node/inery.setup/
```
```
cd tools
```
```
nano config.json
```

AccountName = Ganti dengan nama akunmu

PublicKey = Ganti dengan Public key yang ada diweb

PrivateKey = Ganti dengan Private key mu

IP = Ganti dengan IP address atau DNS 

Save (ctrl+S), lalu "Y" dan exit (ctrl+X)

## 7. Mulai Protocol Blockchain
```
 cd ..
```
```
./ine.py --master
```
Tunggu sampai singkronisasi selesai 

## 8. Jalankan Node
Buka direktori lite.node Lokasi : `cd root/inery-node/inery.setup/master.node/` dan jalankan skrip ./start.sh
Buka Tab baru atau Tab Lain, Jalankan
```
cd ~/inery-node/inery.setup/master.node/
```
```
chmod +x start.sh
```
```
./start.sh
```

## Register and approve wallet

```
cd
```
```
cd;  cline wallet create --file defaultWallet.txt
```
```
cline wallet unlock --password <GANTI_PASSWORDMU>
```
```
cline wallet import --private-key <GANTI_PRIVATE_KEYMU>
```
```
cline system regproducer <GANTI_NAMA_AKUNMU> <GANTI_PUBLIC_KEYMU> 0.0.0.0:9010
```
```
 cline system makeprod approve <GANTI_NAMA_AKUNMU> <GANTI_NAMA_AKUNMU>
```
## DONE 
Silakan cek namamu di exploler kalau ada berarti dah kelar dan tunggu step selanjutnya...
