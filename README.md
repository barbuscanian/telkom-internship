# Fine Tuning: Meningkatkan Kinerja Model AI melalui Data Spesifik
Penjelasan lengkap mengenai pengerjaan fine tuning [disini](https://github.com/barbuscanian/telkom-internship/blob/main/Comparative%20Study%20Mengenai%20Fine%20Tuning.pdf).


Proses penyesuaian model pembelajaran mesin yang telah dilatih sebelumnya untuk meningkatkan kinerjanya dalam tugas atau domain spesifik. Tujuannya adalah agar model dapat memberikan respons yang lebih relevan, akurat, dan sesuai dengan konteks yang diinginkan. Fine-tuning sering digunakan dalam aplikasi seperti chatbot, analisis data, dan rekomendasi, di mana model perlu disesuaikan agar lebih efektif dalam memenuhi kebutuhan pengguna atau situasi tertentu.

![alt text](https://github.com/barbuscanian/telkom-internship/blob/main/img/Fine%20Tuning%20Process.png?raw=true) 

Fine-tuning sangat diperlukan ketika model dasar yang ada terlalu umum dan tidak mampu memberikan hasil yang spesifik sesuai use cases. Dengan fine-tuning, model disesuaikan untuk memahami konteks dan terminologi spesifik dari domain tersebut, sehingga memberikan output yang lebih relevan dan bernilai bagi pengguna.

Dalam proses fine-tuning, yang paling penting untuk disiapkan adalah dataset yang bersih dan relevan. Dataset ini harus terstruktur dengan baik, mencakup data pelatihan dan validasi yang sesuai dengan tujuan fine-tuning, karena kualitas data sangat mempengaruhi hasil akhir model. Setelah itu, hitung token dan estimasi biaya, unggah file ke OpenAI, buat pekerjaan fine-tuning, dan lakukan inferensi serta evaluasi hasil model. Jika perlu, lakukan iterasi untuk penyempurnaan lebih lanjut.

## 1. Fine-Tuning Chatbot Marv dengan Dataset JSONL
![alt text](https://github.com/barbuscanian/telkom-internship/blob/main/img/(1).png?raw=true) 

Bertujuan untuk melakukan fine-tuning pada chatbot Marv, yang dirancang untuk memberikan jawaban faktual dengan sentuhan sarkastik. Dataset yang digunakan berbentuk file JSONL, berisi dialog antara pengguna dan chatbot. Setiap entri mencakup peran pengguna dan respon chatbot, yang mencerminkan gaya sarkasme sambil tetap memberikan informasi akurat. Proses fine-tuning dilakukan melalui dashboard OpenAI, di mana file JSONL diunggah dan diproses untuk meningkatkan kemampuan chatbot dalam memberikan jawaban yang relevan dan menarik.

## 2. Fine-Tuning Model GPT pada Dataset Bank Support Train
![alt text](https://github.com/barbuscanian/telkom-internship/blob/main/img/(2).png?raw=true) 

Bertujuan untuk melakukan fine-tuning dataset yang berisi query dan keluhan pelanggan di bank, dengan fokus pada kategori utama dan subkategori. Prosesnya meliputi beberapa langkah, antara lain:
* Persiapan Dataset: Mengonversi query dukungan menjadi format fine-tuning GPT-3.5, di mana peran pengguna sesuai dengan query, dan peran asisten memberikan respons dalam format JSON yang mencakup kategori utama dan subkategori.
* Pemisahan Data untuk Pelatihan dan Validasi: Dataset dibagi menggunakan metode train_test_split dengan stratifikasi berdasarkan 'Kategori Utama'. Ini memastikan distribusi kategori yang seimbang dalam dataset pelatihan dan validasi.
* Penulisan Data ke Format JSONL: Data yang telah dikonversi disimpan dalam format JSONL, yang cocok untuk fine-tuning GPT-3.5 dengan OpenAI.
* Pengaturan Fine-Tuning: Setelah mengunggah file pelatihan dan validasi ke OpenAI, proses fine-tuning dimulai pada model gpt-3.5-turbo.
* Monitoring Pekerjaan: Proses pemantauan pekerjaan fine-tuning dilakukan dengan mencantumkan pekerjaan yang sedang berlangsung, memeriksa status, serta hyperparameter (misalnya, jumlah epoch, ukuran batch, dll.).

Hasil dari proyek ini diharapkan dapat meningkatkan akurasi dan relevansi respons model dalam menjawab query dan keluhan pelanggan, serta memberikan wawasan yang lebih baik tentang kategori yang sering dibahas oleh pelanggan.

## 3. Fine-Tuning Model GPT pada Dataset Rekomendasi Aksi Sensor
![alt text](https://github.com/barbuscanian/telkom-internship/blob/main/img/(3)1.png?raw=true) 

Bertujuan untuk melakukan fine-tuning model GPT-3.5 pada dataset yang berisi data sensor, dengan fokus pada menghasilkan rekomendasi aksi berdasarkan analisis data yang diberikan. Berikut adalah langkah-langkah yang diambil dalam proyek ini:
*	Instalasi dan Konfigurasi: Proses dimulai dengan menginstal paket OpenAI menggunakan Python. Kunci API OpenAI disetel untuk mengakses model dan fitur yang diperlukan untuk fine-tuning.
*	Upload Dataset: Dataset yang telah dibersihkan dan disiapkan dalam format JSONL diunggah ke OpenAI untuk digunakan dalam fine-tuning. File yang diunggah akan digunakan sebagai data pelatihan untuk mengoptimalkan model.
*	Fine-Tuning Model: Fine-tuning dimulai dengan menggunakan file yang diunggah. Proses ini melibatkan penyesuaian model GPT-3.5 untuk mempelajari pola dari data sensor yang ada, sehingga model dapat memberikan rekomendasi yang lebih akurat berdasarkan input yang diberikan.
*	Monitoring Proses Fine-Tuning: Status dari berbagai pekerjaan fine-tuning dimonitor untuk memastikan bahwa proses berjalan dengan baik. Setiap job yang berhasil dicatat untuk digunakan lebih lanjut.
*	Penggunaan Model yang Sudah Di-fine-Tune: Setelah proses fine-tuning selesai, model yang telah dioptimalkan digunakan untuk melakukan prediksi pada data testing. Pengguna dapat mengirimkan input dalam bentuk data sensor, dan model akan memberikan rekomendasi profesional dalam bentuk teks.
*	Pengolahan Hasil Prediksi: Hasil dari model disimpan dalam format DataFrame, yang kemudian diekspor menjadi file CSV. File ini berisi input yang diberikan, instruksi sistem, dan output yang dihasilkan oleh model, memudahkan analisis lebih lanjut.

Hasil dari proyek ini diharapkan dapat meningkatkan pengambilan keputusan berbasis data dengan memberikan rekomendasi dan bermanfaat berdasarkan pola yang terdeteksi dalam data sensor.

### Perbedaan Sebelum dan Setelah Fine Tuning
![alt text](https://github.com/barbuscanian/telkom-internship/blob/main/img/(3).jpg?raw=true) 

* Sebelum Fine Tuning:
1. Rekomendasi lebih umum dan fokus pada penanganan anomali dalam pola konsumsi daya. Disarankan untuk menyelidiki penyebab anomali, tetapi tidak ada penekanan pada cara mengoptimalkan pola penggunaan.
2.	Meskipun memberikan perhatian pada anomali, saran tidak spesifik tentang bagaimana mengatasi masalah dan memanfaatkan informasi yang ada.

* Setelah Fine Tuning:
1.	Rekomendasi menjadi lebih spesifik dan praktis. Ditekankan untuk memanfaatkan anomali yang terdeteksi sebagai peluang untuk meningkatkan pola penggunaan saat ini.
2.	Rekomendasi juga menekankan pentingnya peninjauan yang lebih terfokus untuk mengoptimalkan hasil, dengan mengaitkan data anomali langsung dengan strategi peningkatan efisiensi.

Dengan fine-tuning, model menjadi lebih terarah dan berorientasi pada hasil dan memberikan instruksi yang lebih jelas tentang bagaimana menggunakan data spesifik untuk meningkatkan efisiensi dan pengambilan keputusan.
