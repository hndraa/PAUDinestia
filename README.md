# JUDUL PROJECT PCD
## Nama Anggota
###  siA : F1D000000
###  siB : F1D000000
###  siC : F1D000000

# Project Overview
Pada project PCD ini, Anda akan melakukan experiment kalsifikasi dengan menggunakan dataset yang telah Anda siapkan sebelumnya. Hal ini bertujuan untuk :
- menguji kemampuan Anda dalam mengimplemetasikan teknik pengolahan citra untuk mengklasifikasikan citra.
- memilih tahapan preprocessing yang tepat sesuai dengan karakteristik data yang ada.

Pemilihan Preprocessing yang digunakan harus menggunakan Preprocessing yang anda telah lakukan dari praktikum Modul 1 - 5. Setelah itu Anda akan melakukan feature extraction dan melakukan pembuatan model klasifikasi.
Perlu di perhatikan bahwa yang menjadi acuan project  adalah tepatnya `preprocessing` dan proses `extraction feature` jadi Anda tidak perlu khawatir dengan hasil akhir dengan akurasi yang mungkin tidak bagus. Selain itu untuk melihat pemahaman Anda dalam analisis Anda akan melakukan eksperimen 3 kali percobaan dengan notebook yang berbeda (format notebook terdapat pada template). Pada setiap percobaannya, Anda diharuskan melakukan improvement pada setiap preprocessing yang telah Anda buat sebelumnya. Anda dapat melakukan improvement dengan cara menyesuaikan jumlah preprocessing pada setiap percobaan. Misalnya, Project anda akan menggunakan total 5 Preprocessing (pre1, pre2, pre3, pre4, pre 5) maka:
- Percobaan Pertama (2 Preprocessing menggunakan pre1, pre2)
- Percobaan Pertama (4 Preprocessing menggunakan pre1, pre2, pre3, pre4)
- Percobaan Pertama (5 Preprocessing menggunakan pre1, pre2, pre3, pre4, pre5)

Lalu dari setiap percobaan lihat bagaimana perbedaan akurasinya untuk setiap model, Random Forest berapa, SVM berapa, KNN berapa. Berokut ini adalah Tahapan Umum yang digunakan dalam Machine Learning. SELAMAT DATANG DI LAB 1

# IMPORT LIBRARY
Anda menginport Library yang dibutuhkan di sini, Anda tidak harus mengikuti dan menggunakan seluruh library yang ada pada template. Library pada template adalah library umum yang sekiranya sering digunakan pada Machine Learning dalam konteks klasifikasi, jadi gunakan library yang di perlukan saja ya.
``` python
  import library
  import library as lib
  import library.library as lib
  from library.library_yang_saya_butuhkan import library, library
```
# Load Data
Setelah Import Library. Selanjutnya tahapan membaca dataset. Pada praktikum modul 1 - 5 Anda pernah membaca beberapa image kedalam code. Pada Project ini Anda tidak hanya akan membaca 1 atau 2 image saja tetapi ratusan bahkan ribuan image bukan hanya image tapi anda akan berurusan dengan label setiap image, jadi sesuaikan code pada template dengan dataset label (Label adalah nama setiap folder pada dataset anda yang berisi image) yang Anda miliki. Pertama-tama lakukanlah data loading(baca dataset) beserta labelnya, Anda bisa melakukan penyeragaman ukuran dari dataset dengan resize, jika ukuran setiap image berbeda pada datset Anda. Misalnya ada yang 100x200, 300x100 maka Anda harus mengubahnya ke ukuran yang sama misalnya 100x100 atau 150x150. Sekedar informasi semakin besar ukuran setiap image maka Loadingnya semakin lama jadi usahakan juga ukuran image rendah, cmiwww
``` python
  data = []
  labels = []
  file_name = []
```
## Data Understanding
Selanjutnya, Anda diminta untuk melakukan eksplorasi data untuk memahami karakteristik data yang digunakan. Anda dapat menampilkan jumlah data, karakteristik data (kondisi background, noise, pencahyaan, dll), distribusi data, sampel data, dan lainnya. Hal ini bertujuan untuk memahami data yang akan digunakan dalam proses klasifikasi, sehingga dapat memilih teknik preprocessing yang tepat ataupun penanganan jika terdapat data yang tidak seimbang. Berikut merupakan contohnya:
``` python
  jumlah.data = []
  jumlah.labels = []
  print(Output: file_name)
```
Output Contoh Visualisasi Distribusi Data: 
![image](https://github.com/user-attachments/assets/bcf4e18c-d6a5-4627-a4d3-c4a2fdb35e8c)
Output: Contoh Sample Data:
![image](https://github.com/user-attachments/assets/0084d31f-386e-49f9-9de5-4863ec4d73de)

# Data Preparation
## Data Augmentation
Pada bagian tahap ini, Anda diwajibkan untuk menerapkan teknik image augmentation untuk menambah jumlah data, JIKA HANYA data Anda berada di rentang 70-100. Anda Bisa melakukan image Augmentation dengan teknik yang ada pada Modul 1
``` python
  augmented.data = []
  augmented.labels = []
  print(Output: file_name)
```
Output: Contoh Image Augmentation
![image](https://github.com/user-attachments/assets/9ea656a7-a69c-47fa-98fc-2a598b81c3a0)

## Preprocessing
Selanjutnya, ini dia Tahap paling krusial Anda dapat melakukan teknik preprocessing yang Anda anggap perlu. Jelaskan alasan Anda menggunakan teknik tersebut, Anda wajib gunakan preprocessing yang ada pada modul-modul yang telah Anda pelajari sebelumnya pada praktikum. Jika Anda merasa preprocessig yang ada pada praktikum tidak sesuai maka silahkan diskusikan dengan Asisten masing" untuk mendapatkan pencerahan.
``` python
def prepro1():
    pass

def prepro2():
    pass

def prepro3():
    pass
```
## Feature Extraction
Pada tahapan ini, Anda diminta untuk melakukan ekstraksi fitur dengan metode Gray Level Co-occurrence Matrix (GLCM). Dengan GLCM sudut 0, 45, 90, dan 135 derajat, simetris, dan lakukan uji coba dengan distance 1-5. Anda dapat menghitung nilai dari beberapa fitur berikut:

- Contrast
- Dissimilarity
- Homogeneity
- Energy
- Correlation
- Entropy
- ASM
``` python
def glcm(image, derajat):
 ...........
```

## Feature Selection
Pada tahap ini, Anda diminta untuk melakukan seleksi fitur. Anda dapat menggunakan teknik seleksi fitur seperti correlation, PCA, atau teknik seleksi fitur lain yang Anda ketahui. NAH PADA TEMPALTE CODE FICTURE SELECTION MENGGUNAKAN CORRELATION YGY.
``` python
correlation = hasilEkstrak.drop(columns=['Label','Filename']).corr()
......
```

## Splitting Data
Pada tahap ini, Anda diminta untuk membagi data menjadi data training dan data testing. Anda dapat menggunakan perbandingan 80:20 atau 70:30 atau 90:10.
``` python
Dataset, Dataset, Dataset, Dataset = train_test_split(Dataset, y, test_size=0.2, random_state=42)
print(Dataset.shape)
print(Dataset.shape)
```

## Normalization
Pada tahap ini, Anda diminta untuk melakukan normalisasi data. Anda dapat menggunakan teknik normalisasi standarization atau min-max normalization.
``` python
Dataset = (Dataset - Dataset.mean()) / Dataset.std()
Dataset = (Dataset - Dataset.mean()) / Dataset.std()
```

# Modeling
Pada tahap ini, Anda diminta untuk membuat model klasifikasi. Berikut merupakan model yang Anda dapat gunakan:
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Random Forest
Gunakan akurasi sebagai metrik yang digunakan untuk menampilkan hasil klasifikasi.
```python
# Train Random Forest Classifier
rf.fit(dataset, dataset)
# Train SVM Classifier
svm.fit(dataset, dataset)
# Train KNN Classifier
knn.fit(dataset, dataset)
```

# Evaluation
Pada bagian ini Anda perlu mengevaluasi model klasifikasi yang telah Anda buat. dengan menampilkan  confusion matrix, dan Clasification Report: accuracy, precision, recall, f1 score. **Jelaskan hasil evaluasi yang Anda dapatkan dan berikan analisis mengenai hasil evaluasi tersebut**.

``` python
def inidiaClassificationReport(dataset, dataset):
	print(classification_report(dataset, dataset))

def plot_confusion_matrix(dataset, dataset, title):
  print(confusion_matrix)
```
Output : Contoh Classsification Report
|               | Accuracy | Precision | Recall   | F1-Score |
| ------------- | -------- | --------- | -------- | -------- |
| KNN           | 0.948667 | 0.948664  | 0.948667 | 0.948504 |
| SVM           | 0.976333 | 0.976319  | 0.976333 | 0.976333 |
| Random Forest | 0.959667 | 0.959822  | 0.959667 | 0.959615 |

Output: contoh confusion matrix
![image](https://github.com/user-attachments/assets/aec4ac9c-e687-4354-b02d-833caf26db6b)


