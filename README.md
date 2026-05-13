# Quiz-Struktur-Data
## Q1-2501010123-IGedeFajarWaradana

## 1.Karakteristik Memori dan Akses Data
Perbedaan kecepatan akses antara Array dan Linked List ditentukan oleh bagaimana mereka disusun di dalam RAM.
- Array (Akses Konstan O(1)):
Array disimpan dalam blok memori yang kontinu (berurutan). Karena ukurannya tetap dan tipenya seragam, komputer dapat menghitung alamat memori elemen ke-i secara langsung menggunakan rumus:
Alamat = Base Address + (index * ukuran elemen)
Inilah yang memungkinkan Random Access secara instan tanpa harus melewati elemen lain.
- Singly Linked List (Akses Linear O(n)):
Node pada Linked List tersebar di lokasi memori yang non-kontinu (acak). Setiap node hanya tahu di mana node berikutnya berada melalui pointer. Untuk menemukan elemen ke-n, sistem harus melakukan traversal mulai dari Head dan mengikuti rantai pointer satu per satu.
## 2. Analisis Efisiensi Operasi Manipulasi
Linked List lebih unggul dibandingkan Array dalam operasi penyisipan (insertion) dan penghapusan (deletion) pada kondisi berikut:
-	Operasi di Awal (Head): Linked List hanya perlu mengubah pointer (O(1)), sedangkan Array harus menggeser seluruh elemen yang ada (O(n)).
-	Ukuran Data Dinamis: Jika frekuensi penambahan/pengurangan data sangat tinggi dan kita tidak tahu ukuran maksimal data di awal, Linked List menghindari biaya penyalinan data (copying) yang sering terjadi pada Array.
-	Alasan Teoritis: Pada Array, penyisipan di tengah memerlukan shifting elemen untuk menyediakan ruang kosong. Pada Linked List, selama kita sudah memiliki referensi ke node tersebut, kita hanya perlu memutus dan menyambung kembali pointer tanpa menyentuh elemen lainnya.
## 3. Konsep Doubly Linked List
Anatomi Node
Berbeda dengan Singly Linked List, setiap node pada Doubly Linked List memiliki tiga komponen utama:
1.	Data: Menyimpan nilai atau informasi elemen.
2.	Next Pointer: Menyimpan alamat memori node setelahnya.
3.	Prev Pointer: Menyimpan alamat memori node sebelumnya.
Dampak dan Fleksibilitas
-	Penggunaan Memori: Lebih tinggi karena setiap node harus menyimpan satu pointer tambahan (prev). Ini menambah overhead memori pada setiap elemen.
-	Fleksibilitas: Memungkinkan penelusuran dua arah (bidirectional traversal). Kita bisa bergerak maju maupun mundur, yang sangat berguna untuk fitur seperti "Undo/Redo" pada aplikasi atau navigasi halaman.
## 4. Mekanisme Circular Linked List
Secara teoritis, yang membedakan Circular Linked List adalah pointer next pada node terakhir tidak menunjuk ke NULL, melainkan menunjuk kembali ke node pertama (Head).
-	Karakteristik: Tidak ada titik akhir yang nyata; struktur ini membentuk loop tertutup sehingga penelusuran bisa dilakukan terus-menerus.
-	Skenario Penggunaan (Use Case): Sistem Penjadwalan Round Robin pada Sistem Operasi. OS memberikan jatah waktu CPU ke beberapa proses secara bergantian. Setelah proses terakhir selesai, CPU langsung kembali ke proses pertama secara otomatis.
## 5. Array Dinamis di Python 
Meskipun terlihat sangat fleksibel, tipe data list di Python secara internal adalah Dynamic Array. Ketika kapasitas internalnya penuh saat melakukan append, terjadi mekanisme berikut:
1.	Alokasi Baru: Python mengalokasikan blok memori baru yang lebih besar (biasanya dengan faktor pertumbuhan tertentu).
2.	Menyalin Data: Semua elemen dari array lama disalin ke blok memori array yang baru secara berurutan.
3.	Penghapusan: Memori array lama dilepaskan/dihapus.
4.	Penyisipan: Elemen baru akhirnya ditambahkan ke ruang kosong yang baru dibuat.


