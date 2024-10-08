***Disclaimer** :Saya mengembangkan alat ini untuk membantu pemilik server mengidentifikasi kerentanan privilege escalation, dan saya tidak mendukung penyalahgunaan X-PrivEsc dalam bentuk apapun. Saya berharap alat ini tidak disalahgunakan.

# X-PrivEsc
Adalah sebuah alat berbasis Python yang dirancang untuk memindai potensi privilege escalation pada sistem berbasis Linux. Alat ini menyediakan berbagai fitur untuk mendeteksi vektor eskalasi hak akses, seperti pencarian file SUID, pengecekan hak sudo, identifikasi file sensitif seperti /etc/passwd dan /etc/shadow, serta pencarian binary yang rentan terhadap eksploitasi. X-PrivEsc juga mengecek versi kernel untuk mengetahui kerentanan yang telah diketahui, memeriksa cron jobs untuk script yang writable, dan memindai direktori dalam PATH serta LD_LIBRARY_PATH untuk mengetahui apakah ada direktori atau library yang memiliki izin insecure. Alat ini memanfaatkan Vulners API untuk mengecek kerentanan CVE pada binary tertentu, memastikan sistem aman dari celah yang bisa digunakan oleh attacker untuk mendapatkan hak akses lebih tinggi.

![X-PrivEsc Logo](img/Screenshot%20from%202024-09-20%2018-24-22.png)

# Fitur X-PrivEsc

1. **Pencarian File SUID (find_suid_files)**:
   - Mencari file dengan bit SUID (Set-User-ID) yang bisa menjadi target privilege escalation jika file tersebut memiliki izin yang salah atau rentan.

2. **Pengecekan Hak Sudo (check_sudo_privileges_extended)**:
   - Mengecek hak sudo pada pengguna saat ini menggunakan perintah `sudo -l` dan memeriksa file `/etc/sudoers` untuk entri **NOPASSWD** yang bisa menjadi celah keamanan.

3. **Pengecekan File Sensitif (check_sensitive_files)**:
   - Mengecek keberadaan dan izin file sensitif seperti `/etc/passwd`, `/etc/shadow`, dan `/etc/sudoers` untuk memastikan file tersebut tidak dapat diakses atau dimodifikasi oleh pengguna yang tidak berhak.

4. **Pencarian Binary Rentan (find_vulnerable_binaries)**:
   - Mencari binary yang rentan (misalnya, `vim`, `nano`, `find`, `awk`, `perl`, `python3`) yang bisa digunakan untuk privilege escalation.

5. **Pengecekan Kerentanan CVE untuk Binary (check_for_cve)**:
   - Menggunakan Vulners API untuk mengecek CVE (Common Vulnerabilities and Exposures) berdasarkan versi binary yang ditemukan.

6. **Pengecekan Versi Kernel (check_kernel_vulnerabilities)**:
   - Mengecek versi kernel sistem operasi dan membandingkannya dengan daftar kernel yang diketahui rentan terhadap eksploitasi.

7. **Pengecekan Port Terbuka (check_open_ports)**:
   - Mengecek port terbuka yang mendengarkan pada sistem untuk mengetahui layanan yang mungkin rentan.

8. **Pengecekan Cron Jobs (check_cron_jobs)**:
   - Mengecek cron jobs yang ada di sistem dan memastikan script yang dieksekusi oleh cron tidak dapat ditulis oleh pengguna yang tidak berhak (writable).

9. **Pengecekan Library Insecure di LD_LIBRARY_PATH (check_insecure_libraries)**:
   - Mengecek **LD_LIBRARY_PATH** untuk library yang memiliki izin insecure (writable), yang dapat digunakan untuk privilege escalation.

10. **Pengecekan Insecurity pada PATH (check_path_insecurity)**:
    - Mengecek direktori yang ada dalam **PATH** dan memastikan tidak ada direktori yang memiliki izin insecure (writable), yang bisa menjadi celah keamanan.

11. **System Logging**
    - Diperuntukan sebagai pencatatan dari hasil scanning

#Installation
1. [![Download ZIP](https://github.com/fierza-dev/X-PrivEsc/blob/main/X-PrivEsc.zip)](X-PrivEsc.zip)
2. cd X-PrivEsc
3. sudo chmod +x *
4. pip install -r requirements.txt
5. Done

#usage
python3 main.pyc


