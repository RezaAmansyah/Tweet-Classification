**Latar Belakang Masalah**

Perkembangan teknologi informasi dan komunikasi telah membawa perubahan besar dalam cara manusia berinteraksi, terutama melalui media sosial seperti Twitter. Platform ini memungkinkan pengguna untuk berkomunikasi, berbagi opini, dan berpartisipasi dalam diskusi global secara instan. Namun, di balik kemudahan tersebut, muncul fenomena negatif berupa **cyberbullying**, yaitu tindakan perundungan yang dilakukan melalui dunia maya. Kasus cyberbullying di Twitter menunjukkan peningkatan signifikan seiring dengan bertambahnya jumlah pengguna dan tingginya aktivitas komunikasi daring. Fenomena ini menjadi perhatian serius karena mampu menyebar dengan cepat dan sulit dikendalikan dalam ekosistem digital yang terbuka.

Cyberbullying memiliki dampak negatif yang luas, baik bagi individu maupun masyarakat. Bagi korban, tindakan ini dapat menimbulkan tekanan psikologis seperti kecemasan, depresi, bahkan keinginan untuk mengakhiri hidup. Dalam konteks sosial, meningkatnya kasus cyberbullying dapat merusak hubungan antarindividu, menurunkan kualitas interaksi di media sosial, serta menciptakan lingkungan komunikasi yang toksik. Oleh karena itu, deteksi dan pencegahan cyberbullying menjadi aspek penting dalam menjaga kesehatan digital masyarakat dan menciptakan ruang daring yang lebih aman serta beretika.

Mendeteksi cyberbullying secara manual pada platform dengan jutaan unggahan setiap harinya, seperti Twitter, merupakan tantangan besar. Volume data yang sangat besar, keragaman bahasa, penggunaan slang, singkatan, dan konteks yang ambigu membuat proses identifikasi ujaran bermuatan perundungan menjadi sulit dilakukan oleh manusia secara efisien. Selain itu, tidak semua ujaran yang bersifat agresif dapat dikategorikan sebagai cyberbullying, sehingga diperlukan pendekatan yang cermat dan sistematis untuk memisahkan konten yang bersifat ofensif dari komentar yang bersifat netral atau bercanda.

Dalam menghadapi tantangan tersebut, kemajuan di bidang **Natural Language Processing (NLP)** dan **machine learning** memberikan solusi yang menjanjikan. Melalui pendekatan ini, komputer dapat dilatih untuk memahami, memproses, dan mengklasifikasikan teks berdasarkan pola linguistik yang menunjukkan indikasi cyberbullying. Teknik-teknik seperti tokenisasi, stemming, lemmatization, dan representasi teks menggunakan metode Bag of Words (BoW) atau TF-IDF memungkinkan sistem untuk mengubah bahasa alami menjadi data numerik yang dapat dipelajari oleh model machine learning. Dengan demikian, proses deteksi dapat dilakukan secara otomatis, cepat, dan konsisten, bahkan terhadap data dalam jumlah besar.

**Tujuan**

Berdasarkan latar belakang tersebut, penelitian atau proyek ini bertujuan untuk membangun model klasifikasi teks yang mampu **membedakan antara ujaran cyberbullying dan non-cyberbullying** secara efisien dan akurat. Model ini diharapkan dapat menjadi dasar bagi pengembangan sistem deteksi otomatis yang membantu platform media sosial maupun lembaga terkait dalam mengidentifikasi dan menanggulangi perilaku perundungan daring. Dengan adanya sistem ini, diharapkan lingkungan digital dapat menjadi lebih aman, sehat, dan produktif bagi seluruh penggunanya.

**Interpretasi Confusion Matrix – Model SVC**

Model SVC menunjukkan performa yang cukup baik dalam mengklasifikasikan data antara kategori *"bully"* dan *"not bully"*.

* **True Positive (bully yang terdeteksi dengan benar):** 7.544
  Angka ini menunjukkan bahwa model berhasil mengenali sebagian besar kasus *bully* secara akurat, yang menandakan kemampuan model yang kuat dalam mendeteksi kategori mayoritas atau kelas target utama.

* **True Negative (not bully yang terdeteksi dengan benar):** 439
  Jumlah ini relatif kecil dibandingkan *true positive*, yang mengindikasikan bahwa model lebih fokus pada identifikasi kelas *bully* daripada *not bully*.

* **False Positive (not bully yang salah diklasifikasikan sebagai bully):** 1.149
  Angka ini menunjukkan bahwa terdapat sejumlah data *not bully* yang salah terdeteksi sebagai *bully*. Dalam konteks implementasi, hal ini dapat menyebabkan kesalahan klasifikasi pada pengguna yang sebenarnya tidak melakukan tindakan *bully*.

* **False Negative (bully yang salah diklasifikasikan sebagai not bully):** 400
  Jumlah ini relatif rendah dibandingkan *false positive*, yang menandakan bahwa model jarang melewatkan kasus *bully* sebenarnya.

**Kesimpulan**

Secara keseluruhan, model SVC menunjukkan **kinerja yang baik dalam mendeteksi kelas "bully"**, dengan tingkat kesalahan yang lebih besar pada *false positive* dibanding *false negative*.
Hal ini berarti model lebih *agresif* dalam mengklasifikasikan suatu teks sebagai *bully*, yang dapat diterima dalam konteks tertentu — misalnya, jika tujuan utama sistem adalah **mendeteksi dan mencegah potensi perundungan secara dini** meskipun berisiko menghasilkan beberapa kesalahan deteksi.

Namun, untuk aplikasi di dunia nyata, **perlu keseimbangan** antara sensitivitas terhadap *bully* dan akurasi terhadap *not bully*, agar sistem tetap adil dan tidak terlalu banyak memberikan *false alert*.



1. Performance Overview
Kelas **Bully** merupakan kelas mayoritas dengan **7944 sampel (~83.3%)**. Model menunjukkan kinerja yang sangat baik untuk mendeteksi kelas ini:

- **Precision:** 0.87  
  Dari semua prediksi “Bully”, 87% benar-benar benar. Artinya, hanya 13% prediksi Bully yang salah, menunjukkan model **tidak terlalu sering false positive** pada kelas ini.

- **Recall:** 0.95  
  Model berhasil menangkap 95% dari semua kasus Bully yang sebenarnya. Ini menandakan model **sangat sensitif terhadap kelas positif**, hampir semua kasus Bully berhasil dideteksi.

- **F1-Score:** 0.91  
  Kombinasi precision dan recall yang tinggi menunjukkan keseimbangan yang baik dan performa yang kuat dalam mendeteksi kelas positif.



2. Confusion Matrix Implications
Berdasarkan confusion matrix:

- **True Positives (TP):** Sebagian besar sampel Bully diklasifikasikan dengan benar.
- **False Negatives (FN):** Hanya sekitar 5% dari kasus Bully gagal terdeteksi. Ini sangat rendah, sehingga risiko **mengabaikan kasus Bully** relatif minimal.
- **False Positives (FP):** Sekitar 13% prediksi Bully sebenarnya Not Bully, yang berarti model cenderung **agresif menandai Bully**, namun dalam konteks deteksi bullying, kesalahan ini mungkin lebih dapat diterima dibandingkan melewatkan kasus nyata.



3. Interpretasi Metrik Lanjutan
- **PR AUC: 0.93**  
  Precision-Recall AUC tinggi menunjukkan model sangat efektif dalam mendeteksi kelas positif bahkan dalam situasi **kelas minoritas relatif kecil**, walaupun kelas Bully adalah mayoritas di dataset ini. Ini memperkuat performa recall tinggi.

- **Weighted Impact:**  
  Karena Bully merupakan mayoritas, performa tinggi pada kelas ini **mendorong weighted average F1 dan recall menjadi tinggi**, yang menjelaskan akurasi keseluruhan yang terlihat tinggi (84%).





