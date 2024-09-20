***Disclaimer** :Saya mengembangkan alat ini untuk membantu pemilik server mengidentifikasi kerentanan privilege escalation, dan saya tidak mendukung penyalahgunaan X-PrivEsc dalam bentuk apapun. Saya berharap alat ini tidak disalahgunakan.

# X-PrivEsc
Adalah sebuah alat berbasis Python yang dirancang untuk memindai potensi privilege escalation pada sistem berbasis Linux. Alat ini menyediakan berbagai fitur untuk mendeteksi vektor eskalasi hak akses, seperti pencarian file SUID, pengecekan hak sudo, identifikasi file sensitif seperti /etc/passwd dan /etc/shadow, serta pencarian binary yang rentan terhadap eksploitasi. X-PrivEsc juga mengecek versi kernel untuk mengetahui kerentanan yang telah diketahui, memeriksa cron jobs untuk script yang writable, dan memindai direktori dalam PATH serta LD_LIBRARY_PATH untuk mengetahui apakah ada direktori atau library yang memiliki izin insecure. Alat ini memanfaatkan Vulners API untuk mengecek kerentanan CVE pada binary tertentu, memastikan sistem aman dari celah yang bisa digunakan oleh attacker untuk mendapatkan hak akses lebih tinggi.

![X-PrivEsc Logo](img/Screenshot%20from%202024-09-20%2018-24-22.png)
