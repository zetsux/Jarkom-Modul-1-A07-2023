# Jarkom-Modul-1-A07-2023

## Deskripsi

Laporan Resmi Praktikum Modul 1 Jaringan Komputer 2023

## Dibuat Oleh
**Kelompok A07**

| Nama | NRP | Link Github |
|---------------------------|------------|--------|
|Dimas Fadilah Akbar | 5025211010 | https://github.com/dimss113 |
|Kevin Nathanael Halim | 5025211140 | https://github.com/zetsux |

### Daftar Soal
- [Soal 1](#Soal-1)
- [Soal 2](#Soal-2)
- [Soal 3](#Soal-3)
- [Soal 4](#Soal-4)
- [Soal 5](#Soal-5)
- [Soal 6](#Soal-6)
- [Soal 7](#Soal-7)
- [Soal 8](#Soal-8)
- [Soal 9](#Soal-9)
- [Soal 10](#Soal-10)

### Soal 1
> User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

Dari kalimat pertama, diperoleh pengetahuan bahwa pengguna melakukan aktivitas menggunakan protokol FTP dan pada kalimat kedua dapat diketahui bahwa aktivitas yang dicari adalah pengunggahan suatu file yang tentunya mengarah ke packet dengan info "STOR". Dari seluruh packet yang ada, diperoleh packet no. 147 sebagai request yang sesuai dengan packet no. 149 sebagai responsenya.

> A. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? <br>
> B. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?

Untuk menjawab kedua pertanyaan di atas, kita hanya perlu mencari kedua nilai tersebut dari packet no. 147 yang berisikan request STOR. Caranya yaitu dengan membuka “Transmission Control Protocol” pada packet tersebut dan bisa dilihat nilainya akan tampil dengan Sequence Number (raw) bernilai **258040667** dan Acknowledgement Number (raw) bernilai **1044861039**

![1AB](https://cdn.discordapp.com/attachments/995337235211763722/1154631552370745405/image.png)

> C. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? <br>
> D. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Untuk menjawab kedua pertanyaan di atas, kita hanya perlu mencari kedua nilai tersebut dari packet no. 149 yang berisikan response dari request STOR. Caranya yaitu dengan membuka “Transmission Control Protocol” pada packet tersebut dan bisa dilihat nilainya tampil dengan Sequence Number (raw) bernilai **1044861039** dan Acknowledgement Number (raw) bernilai **258040696**

![1CD](https://cdn.discordapp.com/attachments/995337235211763722/1154631931368054794/image.png)

#### Dokumentasi Mendapatkan Flag

![1FLAG](https://cdn.discordapp.com/attachments/995337235211763722/1154633036751716422/image.png)

### Soal 2
> Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

- untuk menjawab persoalan tersebut, kita dapat gunakan filter dengan query `tcp cotains "jaringan"`
- kemudian kita bisa follow, kemudian tcp stream dan gunakan filter search dan ketikkan "server" sehingga akan didapatkan server yang digunakan pada portal praktikum Jaringan komputer yaitu "gunicorn"

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/22b62c3f-d71d-498b-8016-8e0c10e081ee)

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/4733d96d-fdb7-4d58-8cbe-09c14bb4fb70)

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/dd2b857c-d84b-4353-8cca-b582c4ab7a6e)


### Soal 3
> Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:<br>
A. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

Untuk menjawab pertanyaan di atas, pertama dimasukkan kueri filter yakni “ip.addr == 239.255.255.250 && udp.port == 3702”. Tujuannya adalah untuk mencari semua paket yang source atau tujuannya memiliki IP 239.255.255.250 yang portnya adalah 3702. Port dicari dengan UDP karena sebelumnya telah dicoba dengan TCP tetapi tidak keluar packet satupun. Hasilnya akan keluar beberapa packet yang bila dihitung jumlahnya bertotalkan **21** packet.

![3A](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/15216841-1520-461d-8638-f6ce7127c6ed)

> B. Protokol layer transport apa yang digunakan?

Untuk menjawab pertanyaan di atas hanya tinggal melihat protocol yang digunakan, yakni yang telah disebutkan sebelumnya yaitu **UDP**

#### Dokumentasi Mendapatkan Flag

![3FLAG](https://cdn.discordapp.com/attachments/995337235211763722/1154633564613259354/image.png)


### Soal 4
> Berapa nilai checksum yang didapat dari header pada paket nomor 130?

Untuk melihat nilai checksum dari paket nomor 130 maka kita perlu scroll seluruh paket hingga sampai ke paket dengan urutan no. 130. Kemudian untuk mengetahui nilai dari checksum kita bisa temukan pada bagian "packet details" pada "User Datagram Protocol".

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/9da4fa10-6322-4e2f-b08d-72e838721df5)

### Soal 5
> Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

 - Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
 - Port berapakah pada server yang digunakan untuk service SMTP?
 - Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

pertama-tama kita harus tahu password dari file yang akan dibuka yang mana nantinya di dalam file tersebut terdapat kode netcat untuk submit 3 jawaban dari 3 soal diatas.
untuk mengetahui password nya dapat kita cari pada packet dengan memfilter menggunakan `tcp contains "pass"`

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/dec31b74-ca7e-487c-8312-fc68dd7c82cb)

kemudian kita buka follow, tcp streams untuk membuka isi paketnya. kemudian kita dapat filter menggunakan kata "word" dan akan akan menemukan passwordnya yaitu sebagai berikut: 

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/7a4db6cd-e7b2-4f33-bb5c-2f0d8ca2b995)

password `NWltcGxlUGFzNXdvcmQ=` dienkripsi dengan base64 sehingga kita perlu melakukan decode terlebih dahulu sehingga didaptkan password nya adalah ``

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/5dc203b1-499e-4625-99b0-b855eb3e057b)


selanjutnya ktia masukkan password pada file connect.txt:

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/fabd75d6-0f71-43b1-b8e0-14d901de6d56)

kemudian lakukan netcat pada terminal dan jawab 3 pertanyaan tersebut:
- pertanyaan 1:
kita dapat mengetahui dengan melihat pada bagian 'packet bytes' dibawah yaitu terdapat 60 paket
![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/64c09e85-156a-4945-828b-11c79fb8f191)

- pertanyaan 2:
untuk mengetahui port smtp kita lakukan filter "smtp" kemudian pada header no 6 kita klik dan lihat pada bagian "packet details" kita dapatkan portnya adalah 25:

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/3861fa06-6504-43aa-957f-ba71bd34bfc3)

- pertanyaan 3:
pertama kita dapatkan semua ip yang tercapture terlebih dahulu:

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/a179c8b6-f1cb-483c-8c15-91acec4e51d4)

Ip yang public adalah `74.53.140.153` karena ip range 10.0.0 hingga 10.255.255 merupakan private ip dan 192.168 juga merupakan private ip.


### Soal 6
> Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan **"server SOURCE ADDRESS 7812 is invalid"**. ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

Penyelesaian dari pertanyaan di atas diawali dari mencari membaca dengan jelas keseluruhan kalimat. Bisa dilihat bahwa terdapat huruf-huruf yang sengaja dibesarkan yang bila disambungkan membentuk kata "SUBSTITUSI" dan juga diberitahu "a1 e5 u21". Dari sana, didapatkan cipher yang digunakan adalah substitution cipher dimana suatu abjad dapat diubah menjadi angka dari urutan abjad tersebut pada alfabet.

Untuk mencari apa yang harus didecrypt dengan cipher tersebut, diperlukan analisis terhadap kalimat "server SOURCE ADDRESS 7812 is invalid". Dari kalimat tersebut dapat diasumsikan bahwa kuncinya terdapat pada alamat ip source dari packet no. 7812 yang bernilai ``104.18.14.101``

![image](https://media.discordapp.net/attachments/997158382429548574/1154641932748857344/image.png)

Bila diencrypt dengan substitution cipher untuk menjadi 6 huruf yang tentunya nilainya di bawah 26 (didapatkan dari hint ke-3 bahwa jawaban terdiri dari 6 huruf) maka akan menjadi sebagai berikut,

```
10 4 18 14 10 1 -> J D R N J A
```

Maka diperoleh jawaban akhir yakni **"JDRNJA"**.

#### Dokumentasi Mendapatkan Flag

![6FLAG](https://cdn.discordapp.com/attachments/997158382429548574/1154643246740406343/image.png) 

### Soal 7
> Berapa jumlah packet yang menuju IP 184.87.193.88?

Pertanyaan di atas dapat dijawab dengan menjalankan query filter yakni “ip.dst == 184.87.193.88" yang bertujuan untuk mendapatkan semua packet dengen alamat ip tujuan adalah ``184.87.193.88``. Setelah difilter, akan tampil **6** packet yang memiliki alamat tujuan tersebut.

![image](https://cdn.discordapp.com/attachments/997158382429548574/1154644410672369734/image.png)

#### Dokumentasi Mendapatkan Flag

![7FLAG](https://cdn.discordapp.com/attachments/997158382429548574/1154644566947934259/image.png) 


### Soal 8
> Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

Query filternya adalah sebagai berikut:
`tcp.dstport == 80 || udp.dstport == 80`

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/9848155b-978f-402c-8012-b750bc5f89a3)


### Soal 9
> Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

Pertanyaan di atas dapat dijawab dengan kueri filter sebagai berikut **"ip.src == 10.51.40.1 && ip.dst != 10.39.55.34"**. Karena paket yang dicari memiliki alamat asal ``10.51.40.1``, maka alamat tersebut dimasukkan sebagai nilai filter dari ``ip.src``. Kemudian untuk kondisi kedua yakni paket tidak menuju ke alamat ``10.39.55.34`` sehingga nilai dari ``ip.dst`` diisi dengan alamat tersebut. Kedua kondisi tersebut dihubungkan dengan operator dan yakni ``&&``.

#### Dokumentasi Mendapatkan Flag

![9FLAG](https://cdn.discordapp.com/attachments/997158382429548574/1154645628132003850/image.png) 

### Soal 10

> Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
- Filter dengan query telnet

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/06b9e033-d644-46ca-8a50-551ad53a9c77)

- Kemudian cari header 236 dan follow tcp streams

![image](https://github.com/dimss113/PBKK-Tugas-Formulir/assets/89715780/f7a8cea7-8eb7-4ec6-9bdd-eabc85aedb8e)

Maka didapatkan password dan username dhafin:kesayangannyak0k0
