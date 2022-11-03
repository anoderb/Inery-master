
<p align="center">
  <img height="50" height="auto" src="https://user-images.githubusercontent.com/38981255/184088981-3f7376ae-7039-4915-98f5-16c3637ccea3.PNG">
</p>

# TASK 2 | Create Token

## 1. BUKA KUNCI WALLET

```
cline wallet unlock -n YourWalletName
```
**YourWalletName** = Nama Wallet Akun Kalian | Jika Wallet Locked Pastikan kalian Memiliki Password Wallet Yang Berada di Dalam `file.txt` Untuk Membukanya

## 2. BUAT ABI & WASM

```
cline get code inery.token -c token.wasm -a token.abi --wasm
```
Paste Saja Langsung Perintah di Atas, Tanpa di Edit

## 3. SET CODE AKUN

**YourAccountName** = Ganti Dengan Nama Node Kalian

```
cline set code -j YourAccountName token.wasm
cline set abi YourAccountName token.abi
```
## 4. CREATE TOKEN BARU

```
cline push action inery.token create '["YourAccountName", "Supply CurrencyCode"], "token description/memo"' -p YourAccountName
```
### Contoh :
```
cline push action inery.token create '["noderb", "50000.0000 CPI"], "Gratis Ongkir Bro"' -p noderb
```
**YourAccountName** = Ganti Dengan Nama Node Kalian
- Buat Symbol Token Bebas dan Deskripsi Bebas dan Supply Coin Samain Aja

## 5. ISSUE NEW TOKEN


```
cline push action inery.token issue '["YourAccountName", "Supply CurrencyCode", "detail"]' -p YourAccountName
```
### Contoh :
```
cline push action inery.token issue '["noderb", "50000.0000 CPI", "Gratis Ongkir Bro"]' -p noderb
```

**YourAccountName** = Ganti Dengan Nama Node Kalian
- Buat Symbol Token Bebas dan Deskripsi Bebas dan Supply Coin Samain Aja

## 6. SEND TOKEN MIN 10 TRANSAKSI ATAU LEBIH KE AKUN ORANG LANGSUNG SAJA PAKE SCRIPT DI BAWAH CUMA EDIT DULU

Yang Harus di Edit

- **YourAccountName** = Ganti Dengan Nama Node Kalian
- **DestinationWalletName =** kaga Usah di Edit Karena Script di Bawah Ini Kumpulan Node Anak Group
- **Amount CurrencyCode** = Isi Berapa Token Yang Akan Anda Kirim Ke Setiap Orang Misalkan `1.0000 CPI` Ganti Dengan Symbol Token Milik Kalian Ini Hanya Contoh
- **Here you go 1 TEST for free :)** = Isi Bebas Ini Hanya Deskripsi Aja

```
cline push action inery.token transfer '["YourAccountName", "inery", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "bgpateng", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "jisoo", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "alfonova", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "dexa", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "jambul.inery", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "riandwiyandi", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "armz", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "asphxwzrd", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "away", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "bintangnl", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
cline push action inery.token transfer '["YourAccountName", "blacktokyoo", "1.0000 CPI", "Here Is 1 TEST for you bro"]' -p YourAccountName
```
### Contoh :
```
cline push action inery.token transfer '["noderb", "inery", "1.0000 CPI", "Gua Lagi baek Nih Bro"]' -p noderb
```


Kalo Udeh, Baru Lu Balik Lagi ke Situs Testnetnya, Klik FINISH dan Tunggu Sampai Review Selesai. Jika di Terima Nanti Akan Terlihat Seperti SS di Atas

**PENTING :** Website Sering Down, Jadi kalian Buka di Mode Penyamaran, Jika Masih Blank Berarti Situs Lagi Down
