# Distance Vector Routing Table
This program has functionality to create routing table by analyzing relationships between nodes and sequence of data delivery

# Implemented By
- Farhan Amin (13515043)
- Stevanno Hero Leadervand (13515082)
- Gianfranco Fertino Hwandiano (13515118)

# How to Run
1. Open terminal in the folder containing the program
2. Type 'make'
3. Type 'distancevector < data/tc.txt'
4. You change the input in tc.txt

# Analysis
## How the Program Works
1. Bagaimana mensimulasikan sebuah node

Kami mensimulasikan sebuah node menjadi sebuah row/colomn pada sebuah array 2d (matriks) dengan ukuran NxN
- pada awalnya elemen-elemen pada matriks, yang adalah edge, diisi dengan nilai false yang menandakan bahwa belum ada koneksi secara langsung antara node-node tersebut
- lalu dilakukan pengisian koneksi antar node berdasarkan inputan yang diberikan. 
- lalu dilakukan pembuatan routing table untuk setiap node dengan membuat array 2d dari struktur data buatan yang berisi distance dan nextHop.
- elemen-elemen tiap matriks menunjukkan info antara row (node yang menjadi fokus) dan column (tetangga), yakni ada distance dan hop. 
- jika row = column yang berarti adalah node yang sama, maka distance disi 0 dan nextHop diisi dirinya row / column.
- jika ada connection[row][column], maka menunjukkan row dan column merupakan node yang merupakan tetangga yang saling terhubung, distance diisi dengan 1 dan nextHop diisi dengan column
- jika row <> column dan tidak ada connection[row][column], maka distance dan nextHop diisi -1

2. Bagaimana proses pengiriman pesan antar node terjadi.
`(Jelaskan dengan menggunakan nama fungsi dan/atau struktur data)`

## Questions
1. Apakah perbedaan dari routing protocol distance-vector dan link state? Manakah yang lebih baik untuk digunakan?

-Link-state routing protocols tahu keseluruhan network dan semua routers punya view yang sama terhadap sebuah network. Sedangkan Distance-vector hanya tahu tentang tetangga yang terhubung langsung dan info tentang cost yang dimiliki oleh tetangga tersebut.
- Link state cepat menuju konvergen, sedangkan distance-vector membutuhkan waktu yang lama untuk mencapai konvergen.
- Link state membutuhkan setiap node untuk sangat bekerjasama, biasanya dibawahi oleh manajemen yang sama, sedangkan distance vector biasanya lebih kuat (tapi tetap rentan terhadap bad information), dan membuat pengguna lebih kreatif, seperti melakukan route filtering.
- Link state jauh lebih kompleks dibanding distance vector yang cenderung simpel.
- Link state membutuhkan spesifikasi hardware yang jauh lebih tinggi dibanding distance vector (Memory, peak CPU load)

tiap protocols punya keunggulan untuk setiap konteks yang ditangani. contohnya distance vector protocols yang memang didesain untuk berjalan pada network yang relatif tidak terlalu besar (kurang dari 100 routers) karena protocol ini secara umum lebih mudah untuk dikonfigurasi dan membutuhkan lebih sedikit maintenance daripada link-state protocols. Tetapi kekurangannya adalah, distance vector tidak scalling dengan baik, karena dibutuhkann penggunaan CPU dan bandwidth yang lebih tinggi, dan juga membutuhkan waktu yang lama untuk konvergen. oleh karena itu, distance-vector protocol hanya cocok untuk network yang relatif kecil. 
Sedangkan link state protocol memang didesain untuk beroperasi pada enterprise-level network   

2. Pada implementasinya saat ini manakah yang lebih banyak digunakan, distance-vector atau  link state? Kenapa?

 

# IF3130 Computer Networks
Bandung Institute of Technology. 2017.