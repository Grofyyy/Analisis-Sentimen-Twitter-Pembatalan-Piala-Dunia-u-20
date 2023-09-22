# Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20
Analisis Sentimen Twitter Terkait Pembatalan Piala Dunia u-20 di Indonesia Menggunakan Metode Support Vector Machine

  Twitter merupakan media sosial microblog yang memungkinkan penggunanya untuk menulis dan berinteraksi berbagai macam topik pembahasan dengan isu isu yang sedang ramai terjadi atau dibicarakan. Dilansir dari Datareportal total pengguna aktif twitter di Indonesia mencapai 24 juta jiwa pada tahun 2023. Dilansir dari We Are Social Twitter menjadi media sosial ke enam terbanyak dari total pengguna media sosial di Indonesia. Jumlah tersebut menunjukan bahwa media sosial twitter menjadi salah satu media di masyarakat Indonesia untuk mendapatkan informasi dan beropini di ruang publik. Dengan banyaknya opini yang tersampaikan di media sosial twitter, maka opini tersebut dapat dijadikan sebagai bahan penilaian untuk mengetahui sentimen masyarakat terkait pembatalan piala dunia U-20 di Indonesia.


## Tujuan Penelitian
Mengimplementasikan algoritma Support Vector Machine untuk menganalisa sentimen mengenai pembatalan piala dunia U-20 di Indonesia tahun 2023 pada media sosial Twitter, Mengukur performa algoritma Support Vector Machine yang digunakan untuk menganalisa sentimen mengenai pembatalan piala dunia U-20 di Indonesia tahun 2023 pada media sosial Twitter dan Mengetahui sentimen dari opini yang diungkapkan masyarakat terkait pembatan piala dunia u-20 pada media sosial twitter.

## Spesifikasi Sitem

  Spesifikasi sistem Perangkat keras (Hardware) dan perangkat lunak (Software) yang digunakan dalam Penelitian ini adalah sebagai berikut:
  1. Perangkat keras (Hardware)
     
    (a) Processor : AMD ryzen 7 5800H,
    (b) RAM : 16GB,
    (c) VGA : NVIDIA GeForce RTX 3060 6gb,
    (d) SSD : SAMSUNG MZVLB1T0HBLR-000L2.
  2. Perangkat lunak (Software)
     
    (a) Windows 11 Home,
    (b) Jupyter notebook,
    (c) Microsoft Edge,
    (d) Python 3.8.

## Crawling Data
  Pengumpulan data yang terkait dengan penelitian ini akan menggunakan library snscrape dan library pandas yang berguna untuk menyimpan data tersebut menjadi dataframe file csv. mengambil tweet yang menggunakan bahasa Indonesia dengan kata kunci kata kunci ”piala dunia u 20” dan tanggal pengambilan yang dimulai dari 30 Maret 2023 hingga 05 April 2023. Setelah kata kunci telah dibuat selanjutnya adalah mendeklarasikan data yang akan diambil berupa tanggal, username dan tweet. Kemudian data tersebut akan disimpan ke dalam dataframe yang terdiri dari tiga kolom yang menampung hasil dari pengambilan data tersebut.

  <img width="470" alt="CrawlingData" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/6a4f0e8a-6bcd-46cd-a502-634977e5e10c">

## Labeling Data
### Translated Data
  Melakukan Pelabelan Data  yang berguna untuk memberikan n label positif, negatif atau netral dari data yang telah dikumpulkan. Pada tahap ini akan dilakukan pelabelan menggunakan VADER sebelum menggunakan VADER perlu dilakukan translate data bahasa Indonesia ke bahasa inggris dikarenakan library VADER hanya bisa membaca data yang menggunakan bahasa inggris.

<img width="587" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/5cc815d6-1d9b-4f85-9497-b68afa571f43">

### Labeling Data dengan VADER
  Setelah data teks telah berhasil di translated ke dalam bahasa inggris. Langkah selanjutnya adalah melakukan perhitungan menggunakan VADER. Dalam menggunakan VADER perlu mengimport library dari nltk.sentiment.vader yaitu SentimentIntensityAnalyzer

<img width="334" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/d9cd9231-425c-4c35-bef0-6920f9f6c28d">

Hasil pelabelan dari 14807 data yang telah dikumpulkan. Dari data tersebut menghasilkan bahwa 33.40% memiliki sentiment positif, 45.71% memiliki sentiment negatif dan 20.88% memiliki sentiment netral.

![Pie_Chart_Labelpng](https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/2460d677-49a0-4b61-8fff-e1b12a01bc05)

## WorldCloud

World Cloud merupakan daftar kata yang sering muncul antara label positif, negatif dan netral.

### Positif Sentiment

![image](https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/5324fa92-65b2-440f-b095-74ae59423dae)

### Negatif Sentiment

![image](https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/f8003098-9cc8-4e76-8f71-5a1672e84d18)


### Netral Sentiment

![image](https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/ea0452bf-b8e6-4dc5-90b4-a56732ea59bb)

## Text Pre-processing
Setelah berhasil dilakukan Pelabelan langkah selanjutnya adalah melakukan Text Pre-processing. Tahapan ini merupakan proses untuk menyeleksi data text agar menjadi terstruktur. Karena teks yang ingin dilakukan analisis sentimen berbahasa Indonesia maka kolom yang akan disimpan dalam data adalah teks berbahasa Indonesia dan Label. Text Pre-processing memiliki beberapa tahapan yaitu case folding, cleaning data, tokenizing, normalisasi, stopwords dan stemming.

### Case folding
Case Folding merupakan tahapan yang berfungsi untuk menyamaratakan huruf pada teks menjadi huruf kecil.

<img width="544" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/1037ac6e-70d5-4f26-9dd6-7c9d9aa13b66">

### Cleaning Data
Setelah tahap case folding telah berhasil dilakukan selanjutnya Tahapan melakukan seleksi dengan membersihkan teks dari username, hastag, symbol, emoticon, link, single char, number, whites pace dan punctuation.

<img width="381" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/f5b63757-fbdb-4a3b-8c68-7dfb76e38463">

### Tokenizing 
Tokenizing yang berfungsi untuk merubah kalimat yang ada menjadi daftar kata berfungsi untuk proses normalisasi, stopword dan steming.

<img width="287" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/74dc9097-41f7-455d-8c0a-a5e2113fb7eb">

### Normalisasi
Normalisasi bertujuan untuk memperbaiki kata singkat yang tidak baku
menjadi kata dasar yang baku. Contoh penggunaan normalisasi seperti kata
”sdg” menjadi kata ”sedang”.

<img width="221" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/3564b6dd-ff66-4ce0-b40b-67b1b52122ea">

### Stop Words
Tahapan stopwords berfungsi untuk memilih kata kata yang dianggap penting dalam teks dan membuang kata kata yang tidak mempunyai arti seperti kata
penghubung.

<img width="170" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/99a1dcdb-3c4f-4bc9-a8fe-92aba89b21a1">

### Stemming

Stemming merupakan tahapan mengekstrak bentuk kata dasar dengan
menghilangkan kata imbuhan. Contoh penggunaan stemming adalah kata
”seindonesia” menjadi ”Indonesia”.

<img width="127" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/592797ce-7dba-4c7c-997e-8a71f722eb41">

## Train-Test Split Data

Train-Test split data merupakan teknik dalam machine learning untuk
membagi data menjadi data train dan data test. Proses ini dilakukan untuk menilai
kinerja pemodelan dalam machine learning.

## Apply TF-IDF

setelah data melaui tahapan Train-Test Split Data
selanjutnya akan dilakukan pembobotan kata menggunakan TF-IDF dan
menghasilkan Train (TF-IDF) dan Test (TF-IDF). Tahapan ini dilakukan untuk
mengimplementasikan pemodelan klasifikasi menggunakan SVM.

## Evaluasi Model

Setelah proses prediksi telah dilakukan untuk melihat nilai hasil
beserta kinerja dari prediksi tersebut dapat menggunakan confusion matrix dan
classification report untuk menampilkan detail dari accuracy, precision, recall, f1
score dalam table confusion matrix.

## Uji Coba

Pada tahap ini akan dilakukan skenario pengujian dan masing masing
skenario akan dievaluasi sehingga dapat dilihat manakah yang dapat memberikan
performa terbaik. Skenario uji coba analisis sentimen penelitian ini sebagai berikut:

1. Melakukan perbandingan kernel linear, polynomial dan rbf pada metode
Support Vector Machine. Hal ini dilakukan untuk mencari kernel mana yang
dapat menghasilkan tingkah performa yang lebih baik.
2. Melakukan perbandingan data training dan testing sebanyak 60:40, 70:30 dan
80:20. Hal ini dilakukan untuk mengukur tingkah Performa pemodelan yang
telah dibuat dan seberapa pengaruhnya perbandingan data training dan testing
dalam analisis sentimen.
3. Dari data yang telah didapatkan akan dilakukan training untuk menguji
metode SVM dalam menganalisa data yang dimasukan atau diinput secara
external.

## Pengujian dengan Pembagian Data Training dan Data Testing

Pada tahap pengujian ini akan dilakukan pembagian data training dan testing
sebanyak 60:40, 70:30 dan 80:20 dari 14807 total data yang telah dikumpulkan.
Data training yang telah dibagi akan digunakan untuk dipelajari oleh sistem
kemudian data testing akan digunakan untuk menguji sistem yang telah dibuat untuk
memprediksi analaisis sentimennya.

<img width="344" alt="image" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/9d91c3e3-2d9e-4625-8573-57a78fa25692">

setelah dilakukan pengujian dengan pembagian data training dan data testing didapatkan hasil bahwa
kernel linear, polynomial dan rbf mendapatkan penilian terbaik dari pembagian
dataset 80:20 dan kernel rbf mendapatkan hasil yang lebih baik dibanding kernel
linear maupun polynomial dengan mendapatkan hasil Accuracy 78.15%, F1-Score
76.30%, Precision 77.37% dan Recall 75.58%.

## Pengujian dengan Input teks Berbahasa Indonesia
  
<img width="536" alt="Hasil_InputTeks" src="https://github.com/Grofyyy/Analisis-Sentimen-Twitter-Pembatalan-Piala-Dunia-u-20/assets/92924319/39643b37-da22-4d76-a4a6-18b6ca1b4584">

Gambar diatas merupakan hasil dari analisis sentimen sesuai dari input
teks berbahasa indonesia. Hasil tersebut didapatkan dari data training yang telah
di lakukan pembelajaran ke sistem menggunakan metode Support Vector Machine
sehingga sistem dapat menganalisa teks berbahasa Indonesia dan digolongkan
menjadi sentiment positif, negatif atau netral.

## Simpulan 

1. Penelitian Alisis Sentimen Twitter Terkait Pembatalan Piala Dunia u-20 di
Indonesia Menggunakan Metode Support Vector Machine telah berhasil
dilakukan dan dapat digunakan untuk melakukan analisis sentimen terkait
topik pembahasan berbahasa Indonesia. Dari hasil analisa sentimen
menggunakan algoritma Support Vector Machine didapatkan bahwa kernel
rbf mendapatkan penilaian yang lebih baik dibanding kernel linear dan
polynomial. Pembagian data train dan data test menunjukan jika Semakin
banyak data training yang digunakan maka hasil akurasi yang diberikan akan
semakin lebih baik.
2. Dari 14807 data yang telah dikumpulkan sebanyak 45.71% memiliki
sentimen negatif, 33.40% memiliki sentimen positif dan 20.88% memiliki
sentimen netral. Hal ini menunjukan dari analisa sentimen pada media sosial
twitter terkait pembatalan piala dunia U-20 di Indonesia tahun 2023 bahwa
sentimen negatif mempunyai peresentase data yang lebih tinggi dibandingkan
sentimen lainnya.










