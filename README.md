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

2. Handle Duplicated Data <br>
Untuk mengecek adanya data yang duplikat, dapat dilakukan dengan menggunakan fungsi sebagai berikut : <br>
df.duplicated().sum(). Hasil menunjukkan bahwa pada dataset ini tidak terdapat data yang duplikat, sehingga dataset ini bisa dianalisis lebih lanjut.

3. Handle outliers <br>
Dalam handle outliers kami memutuskan untuk menghapus baris - baris pada kolom yang memiliki outlier dengan menggunakan rumus sebagai berikut :
Batas bawah = Q1 - 1,5 x IQR
Batas atas    = Q3 + 1,5 x 1QR
Pada dataset terdiri dari beberapa outliers. Hal ini dapat diatasi dengan menggunakan metode machine learning yang dapat menangani outliers atau robust terhadap outliers.

4. Feature Transformation <br>
Feature transformation dilakukan dengan menggunakan Label Encoding yaitu mengubah setiap nilai dalam kolom menjadi angka yang berurutan. Pada bagian ini kami melakukan Label Encoding pada feature kategorik sebagai berikut : NewExist, UrbaRural, RevLineCr, LowDoc, MIS_Status. <br>
Kemudian pada data numerik, dilakukan standarisasi dengan menggunakan library sklearn.preprocessing dengan fungsi StandardScaller. Hal ini dilakukan agar data numerik memiliki skala yang sama sehingga memudahkan dalam analisis dan pemodelan machine learning. Feature yang dilakukan standarisasi diantaranya adalah sebagai berikut :  ApprovalFY, Term, NoEmp, CreateJob, RetainedJob, DisbursementGross, BalanceGross, ChgOffPrinGr, GrAppv, SBA_Appv.

8. Feature Encoding
Feature Encoding dilakukan pada feature yang bersifat kategorik. Pada tahap ini kami melakukan feature encoding pada feature-feature beriktu : <br>
MIS_Status <br>
CHGOFF = 1 dan PIF = 0   <br>
RevLinCr  <br>
Yes = 1 dan No = 0  <br>
LowDoc  <br>
Yes = 1 dan No = 0  <br>
UbanRural  <br>
Yes = 1 dan No = 0  <br>

10. Handle Class Imbalance
Pada dataset ini terlihat bahwa pada feature MIS_Status imbalance. Pada tahap ini, kami belum melakukan oversampling/undersampling dikarenakan kami ingin mengidentifikasi terlebih dahulu pada saat pemodelan machine learning dan akan dilakukan evaluasi setelah pemodelan.

12. Feature SelectionBerdasarkan scatterplot yang telah dilakukan pada stage sebelumnya, terlihat bahwa terdapat beberapa feature yang memiliki korelasi yang kuat sehingga perlu dipilih salah satu feature saja yang bisa dilakukan analisis.Feature yang memiliki korelasi yang kuat diantaranya adalah : CretaeJob dan RetainedJob, DisbursementGross dan GrAppv, DisbursementGross dan SBA_Appv, GrAppv dan SBA_Appv. Berdasarkan hasil scatterplot maka feature yang akan dihilangkan salah satu adalah antara lain CreateJob, RetainedJob, DisbusermentGross, SBA_Appv & GrAppv.

14. Feature Extraction
Pada Feature Extraction, kami melakukan segmentasi pada feature ‘UrbanRural’, dengan kategori <= 0 adalah ‘Undefined’, <= 1 adalah ‘urban’, dan sisanya adalah ‘rural’. <br>
Pada feature ‘GrAppv’ dan ‘SBA_Appv’ juga dilakukan segmentasi berdasarkan range nilai minimal dan maksimalnya. Hasil dari range pada masing-masing feature lalu dibagi menjadi 3 kelas, yakni low, mid, high. <br>
Feature ‘NAICS’ berisi kode-kode terkait jenis industri dari peminjam. Pada feature ini akan dilakukan segmentasi terkait industri bisnis mana yang memiliki risiko tinggi bagi peminjam dan penjamin. NAICS dengan kode berawal 44, 45, 48, 49, dan 56 adalah kode yang mewakili jenis industri dengan risiko tertinggi, yakni Transportation & Warehousing; Retail Trade; dan Administrative Support & Waste Management. NAICS dengan kode tersebut akan didefinisikan sebagai risiko “high”, sementara yang lainnya akan didefinisikan sebagai risiko “low”
