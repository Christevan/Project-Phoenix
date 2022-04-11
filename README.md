EMPLOYEE ATRITION – PHOENIX TEAM 
A.	MODELING
1.	Split Data Training dan Test
 
	Kami menggunakan train test split sebelum handle class imbalance agar data yang dibalancing merupakan data train saja bukan dengan data test. Kami menghindari data leaks dan memberikan data hasil balancing ke data test, atau dengan kata lain kami menjaga data test tetap original. Kami membagi data menjadi 80% data train dan 20% data test.
 
2.	Handle Class Imbalance
 
Berdasarkan hasil percobaan handle class imbalance tersebut kami menyimpulkan dan menetapkan metode SMOTE yang akan digunakan sebagai metode untuk step ini. Hal tersebut dikarenakan jumlah data yang sedikit akan membuat data tidak akan terrepresentasikan dengan baik jika menggunakan metode undersampling.

3.	Modeling
 
Kami menggunakan banyak scenario dalam pemodelan tersebut. Karena data yang kecil membuat kami kesulitan untuk menentukan model yang terbaik. Hasil dari sekian banyak scenario kami masih menghasilkan hasil score yang bisa dibilang buruk. 

4.	Model Evaluation: Pemilihan dan Perhitungan Metrics

Kami berfokus untuk metric scoring Recall karena kami ingin focus pada False Negative. Kami berpikir lebih baik memberikan treatment kepada employee yang sebenarnya tidak atrisi daripada tidak memberikan mengabaikan karyawan yang sebenarnya atrisi. Itu akan berdampak baik karena akan menambah satisfactory rate karyawan kepada perusahaan dan memperkecil peluang atrisi karyawan lain. Hal ini kami fokuskan karena dari research kami, biaya hiring lebih besar daripada mempertahankan karyawan. Hasil terbaik yang kami dapat untuk saat ini adalah 0.67 untuk train set dan 0.64 untuk test set.

5.	Model Evaluation: Apakah Model Sudah Best Fit?

Kami memiliki scenario dengan hasil model yang sudah best fit, namun demikian nilai dari metric – metricnya masihsangat rendah terutama untuk recall yang merupakan primary metrics kami sehingga masih perlu adanya perbaikan dan pengkajian ulang.

6.	Hyperparameter Tuning
 
Kami menggunakan Randomized Search pada hyperparameter tuning untuk hampir keseluruhan scenario karena hasil dari Grid Search selalu lebih buruk. Scoring metrics yang kita pakai adalah recall sesuai dengan point sebelumnya. Estimator – estimator yang kita pakai juga estimator yang umum saja.

B.	FEATURE IMPORTANCE
1.	Feature Importance
 
Berikut adalah salah satu hasil feature importance dari scenario yang kami buat. Dapat dilihat bahwa top 5 dari feature importance kami adalah MonthlyIncome, Age, DistanceFromHome, TotalWorkingYears, StockOptionLevel, dan OverTime. Urutan dari grafik ini menunjukkan seberapa pengaruhanya fitur tersebut terhadap target yakni atrisi.

2.	Feature Selection
 
Kami mencoba untuk melakukan pemodelan ulang menggunakan 5 fitur paling berpengaruh berdasarkan analisis sebelumnya. Hasil yang didapatkan masih tidak menghasilkan nilai yang baik dan best fit. Oleh karena itu, kami menyimpulkan bahwa analisis kami masih perlu diperbaiki dari preprocessing hingga ke pemodelannya.
