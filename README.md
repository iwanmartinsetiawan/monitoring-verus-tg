# monitoring-verus-tg
Script untuk monitoring temperatur, uptime, ip address, hostname, hashrate verus, last share verus di armbian.

# How to install
1. Silahkan seting terlebih dahulu auto start minernya, menggunakan script di link berikut :  
https://github.com/iwanmartinsetiawan/verus-auto-armbian

2. Jika belum punya bot telegram, silahkan bisa dibuat terlebih dahulu. Caranya bisa mengikuti link berikut :  
http://bit.ly/reg-bot-telegram

3. Cek id telegram kita, sebagai penerima notifikasinya. Dengan cara berikut :  
http://bit.ly/cek-id-telegram

4. Buka terminal armbiannya. Lalu masukkan command berikut :  
```
wget -L https://raw.githubusercontent.com/iwanmartinsetiawan/monitoring-verus-tg/main/monitoring.sh
```
5. Edit file monitoring.sh yang telah didownload sebelumnya, menggunakan command dibawah :  
```
nano monitoring.sh
```
  - <TOKEN_BOT_TELEGRAM> ganti dengan token bot yang didapatkan dari hasil step 2.  
    Contoh : 123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11
  - <ID_TELEGRAM> ganti dengan ID chat penerima yang didapatkan dari step 3.

Kemudian save and quit. Dengan cara tekan tombol CTRL+X, tekan tombol Y dan enter.

6. Sekarang seting untuk schedulenya, dengan cara masukkan command berikut :  
```
crontab -e
```
7. Tambahkan script berikut dibaris terakhir/paling bawah :  
```
*/5 * * * * bash /root/monitoring.sh > /root/monitoring.log 2>&1
```
*/5 di script diatas artinya perintah monitoring akan dijalankan per 5 menit. Silahkan bisa disesuaikan dengan kebutuhan.  
Untuk mengetahui penulisan dan arti dari crontab, bisa mengunjungi link dibawah :  
https://crontab.guru/

8. Save and Quit, dengan cara tekan tombol CTRL+X, tekan tombol Y dan enter. 
