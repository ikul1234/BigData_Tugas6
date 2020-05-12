## Bigdata 2020

# Tugas 5 Big DATA

- [Tugas 5 Big DATA](#tugas-5-big-data)
- [MLlib model to PMML](#mllib-model-to-pmml)
  - [Business Understanding (MLib)](#business-understanding-mlib)
  - [Data Understanding (MLib)](#data-understanding-mlib)
  - [Data Preparation (MLib)](#data-preparation-mlib)
  - [Modeling (MLib)](#modeling-mlib)
  - [Evaluation (MLib)](#evaluation-mlib)
  - [Deployment (MLib)](#deployment-mlib)
  - [Workflow Keseluruhan](#workflow-keseluruhan)
- [Spark Compiled Model Predictor](#spark-compiled-model-predictor)
  - [Business Understanding (Spark)](#business-understanding-spark)
  - [Data Understanding (Spark)](#data-understanding-spark)
  - [Data Preparation (Spark)](#data-preparation-spark)
  - [Modeling (Spark)](#modeling-spark)
  - [Evaluation (Spark)](#evaluation-spark)
  - [Deployment (Spark)](#deployment-spark)

# MLlib model to PMML
## Business Understanding (MLib)
Kemungkinan-kemungkinan yang dapat dilakukan yaitu dari data tersebut, dapat dilakukan proses klasifikasi terhadap dataset bunga bunga iris yang tersedia. Dari sini juga dapat dijadikan pembelajaran untuk memahami
machine learning model.
## Data Understanding (MLib)
- Dataset iris ini terdiri dari 150 row dan 6 coloumns, dataset ini mengandung 3 spesies iris dengan memiliki 50 <br/>
  sampel masing-masing, serta menyampaikan beberapa informasi atau properti tentang masing-masing bunga.
  
- coloumn unique di representasi oleh id

- dataset berisi csv sebagai berikut :
  - id
  - SepalLength(Cm)
  - SepalWidth(Cm)
  - PetalLength(Cm)
  - PetalWidth(Cm)
  - Species (Iris setosa, iris versicolour, iris virginica)

## Data Preparation (MLib)
- Pertama, siapkan node file reader untuk membaca file </br>
  ![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/1.jpg "DPPertama")<br/>
- Kedua, atur node file reader tersebut dengan mengarah ke dataset iris</br>
  ![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/2.jpg  "DPKedua")<br/>
- Ketiga, siapkan node local big data environtment</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/3.jpg "DPKetiga")<br/>
- Keempat, atur pada node local big data environment</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/4.jpg "DPKeempat")<br/>
- Kelima, siapkan node Table to Spark</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/5.jpg "DPKelima")<br/>
- Keenam dapatlah hasil seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/6.jpg"DPKeenam")<br/>


## Modeling (MLib)
- Pertama, gunakan node Spark k-Means untuk melakukan train pada tabel sebelumnya</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/7.jpg"MPertama")<br/>
- Kedua, atur node Spark k-Means seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/8.jpg"MKedua")<br/>
- Ketiga, gunakan node Spark MLIB to PMML agar mengubah model dari spark menjadi PMML</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/9.jpg"MKetiga")<br/>
- Keempat, gunakan node PMML Compiler agar bisa dijalankan oleh node Compiled Model Predictor</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/10.jpg"MKeempat")<br/>
- Kelima, setting PMML Compiler seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/11.jpg"MKelima")<br/>


## Evaluation (MLib)
- Pertama, ambil data lagi dari File Reader sebagai test data</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/12.jpg"EPertama")<br/>
- Kedua, atur File Reader seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/13.jpg"EKedua")<br/>
- Ketiga, gunakan node Compiled Model Predictor untuk mendapati hasil dari entropynya</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/14.jpg"EKetiga")<br/>
- Keempat, dapat dicek hasil dari Compiled Model Predictor pada gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/15.jpg"EKeempat")<br/>
- Kelima, gunakan node Entropy Scorer untuk melakukan perhitungan</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/16.jpg"EKelima")<br/>
- Keenam, cek hasil perhitungan tersebut seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/17.jpg"EKeenam")<br/>


## Deployment (MLib)
- Pertama, dari data yang sudah diprediksi, kita gunakan node dengan format json, dan gunakan node JSON to Table</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/18.jpg"DPertama")<br/>
- Kedua, atur pada node Container Input (JSON) seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/19.jpg"DKedua")<br/>
- Ketiga, gunakan node Compiled Model Predictor, Table to JSON, dan Container Output (JSON)</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/20.jpg"DKetiga")<br/>
- Keempat, setelah dijalankan semua akan ada hasil seperti gambar di bawah</br>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/21.jpg"DKeempat")<br/>


## Workflow Keseluruhan
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/22.jpg"WFKeseluruhan")<br/>


# Spark Compiled Model Predictor
## Business Understanding (Spark) 

Kemungkinan-kemungkinan yg dapat dilakukan yaitu dari data tersebut, dapat dilakukan proses klasifikasi menggunakan berbagai algoritma terhadap dataset bunga bunga iris yang tersedia. Dari sini juga dapat dijadikan pembelajaran untuk memahami machine learning model.

## Data Understanding (Spark)

- Dataset iris ini terdiri dari 150 row dan 6 coloumns, dataset ini mengandung 3 spesies iris dengan memiliki 50 <br/>
  sampel masing-masing, serta menyampaikan beberapa informasi atau properti tentang masing-masing bunga.
  
- coloumn unique di representasi oleh id

- dataset berisi csv sebagai berikut :
  - id
  - SepalLength(Cm)
  - SepalWidth(Cm)
  - PetalLength(Cm)
  - PetalWidth(Cm)
  - Species (Iris setosa, iris versicolour, iris virginica)

## Data Preparation (Spark)
- memasang node file reader untuk membaca dataset<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/23.jpg "DP1")<br/>

- melakukan pengaturan terhadap node file reader<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/24.jpg "DP2")<br/>

- memasang node decision tree learner<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/25.jpg "DP3")<br/>

- melakukan pengaturan terhadap node decision tree learner<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/26.jpg "DP4")<br/>

- memasang node mlp learner<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/27.jpg "DP5")<br/>

- melakukan pengaturan terhadapt node mlp learner<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/28.jpg "DP6")<br/>

- workflow dari data preparation<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/29.jpg "DP7")<br/>


## Modeling (Spark)
- berikut adalah workflow modeling ,melakukan pemasangan node concatenate untuk menggabungkan dua learner yang berbeda<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/30.jpg "M1")<br/>

- melakukan pemasangana table to pmml ensemble untuk menggabungkan tabel dokumen pmml menjadi satu dengan model mining<br/>
  untuk dilakukan compiler<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/31.jpg "M2")<br/>

- dan yang terakhir node pmml compiler untuk menganti model pmml ke java bytecode agar bisa dijalankan<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/32.jpg "M3")<br/>


## Evaluation (Spark)
 - merupakan workflow dari proses evaluation<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/33.jpg "E1")<br/>

- menambahkan data untuk test, dengan konfigurasi seperti ini<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/34.jpg "E2")<br/>

- memasang node table to spark agar bisa di eksekusi<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/35.jpg "E3")<br/>

- dan didapati hasil di node spark compiled model predictor seperti ini<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/36.jpg "E4")<br/>


## Deployment (Spark)
- merupakan workflow dari proses deployment<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/37.jpg "D1")<br>

- di tahap ini kita merubah data ke dalam table, dan didapati hasil dalam node scorer seperti ini<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/38.jpg "D2")<br>

- jika ingin dideploy ke bentuk csv akan seperti ini <br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/39.png "D3")<br>

- workflow secara keseluruhan<br/>
![alt text](https://github.com/ikul1234/BigData_Tugas6/blob/master/Screenshot/40.jpg "D4")<br>
