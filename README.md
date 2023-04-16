# Data-Preprocessing-Kelompok-10-10
Data Preprocessing pada data SBAnational.csv
1. Handle Missing Values <br>
Sebelum dilakukan handle missing value, kami melakukan pengubahan tipe data yang sesuai terlebih dahulu. Untuk mengecek adanya missing value digunakan fungsi sebagai berikut : df.isna().sum()<br>
Hasil output tersebut diketahui bahwa semua feature memiliki nilai missing value. Terdapat 1 feature yang memiliki nilai missing value >80% yaitu feature ChgOffDate, sedangkan feature lainnya hanya memiliki nilai missing value < 0,005%. Untuk feature ChgOffDate feature ini akan dihapus dan tidak digunakan untuk analisis, sedangkan untuk future lainnya akan dilakukan penghapusan pada baris yang memiliki missing value.<br>
Setelah dilakukan penghapusan kolom dan baris, akan dicek kembali menggunakan fungsi : df.isna().sum(). Hasil fungsi tersebut terlihat bahwa sudah tidak ada lagi missing value pada dataset. Selain handle missing value, kami juga melakukan cleaning pada beberapa feature diantaranya adalah sebagai berikut : <br>
Cleaning feature ‘ApprovalFY’ <br>
Feature ini seharusnya berisi data tahun namun pada baris tertentu terdapat baris yang berisi ‘1976A’. <br>
Cleaning feature ‘NewExist’  <br>
Feature ini seharusnya hanya berisi data nominal 1 dan 2 saja, namun pada data terdapat angka 0. <br>
Cleaning Feature ‘RevLineCr’ dan ‘LowDoc’ <br>
Feature ini memiliki beberapa karakter yang harus dihapus. <br>

2. Handle Duplicated Data
3. Handle outliers
4. Feature Transformation
5. Feature Encoding
6. Handle Class Imbalance
7. Feature Selection
8. Feature Extraction
