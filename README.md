# Data-Preprocessing-Kelompok-10-10
Data Preprocessing pada data SBAnational.csv
1. Handle Missing Values <br>
Sebelum dilakukan handle missing value, kami melakukan pengubahan tipe data yang sesuai terlebih dahulu. Untuk mengecek adanya missing value digunakan fungsi sebagai berikut : 

df.isna().sum()

Hasil output tersebut diketahui bahwa semua feature memiliki nilai missing value. Terdapat 1 feature yang memiliki nilai missing value >80% yaitu feature ChgOffDate, sedangkan feature lainnya hanya memiliki nilai missing value < 0,005%. Untuk feature ChgOffDate feature ini akan dihapus dan tidak digunakan untuk analisis, sedangkan untuk future lainnya akan dilakukan penghapusan pada baris yang memiliki missing value. 
 
2. Handle Duplicated Data
3. Handle outliers
4. Feature Transformation
5. Feature Encoding
6. Handle Class Imbalance
7. Feature Selection
8. Feature Extraction
