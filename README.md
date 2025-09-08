Deskripsi: Sebuah universitas ingin mengimplementasikan sistem evaluasi nilai akhir mahasiswa yang komprehensif. Sistem ini harus mampu menghitung nilai akhir berdasarkan beberapa komponen, menerapkan kondisi khusus, dan menentukan grade huruf serta status kelulusan. Anda diminta untuk membuat program C yang menerima detail seorang mahasiswa, melakukan perhitungan, dan menampilkan hasilnya sesuai format yang ditentukan.
Input: Program Anda harus menerima lima jenis input dari keyboard:
1. Nomor Registrasi Pokok (NRP): Bilangan bulat yang sangat besar untuk identifikasi mahasiswa. Gunakan tipe data yang sesuai untuk menyimpan bilangan yang sangat besar ini.
2. Nilai Tugas: Bilangan desimal.
3. Nilai Ujian Tengah Semester (UTS): Bilangan desimal.
4. Nilai Ujian Akhir Semester (UAS): Bilangan desimal.
5. Persentase Kehadiran: Bilangan desimal yang menunjukkan kehadiran mahasiswa (antara 0.0 hingga 100.0).
Perhitungan dan Kondisi Khusus: Program harus melakukan perhitungan berikut:
• Rata-rata Nilai Utama (RataUtama): Dihitung dari (Nilai Tugas + Nilai UTS + Nilai UAS) / 3. Gunakan operator aritmatika.
• Poin Penalti Absensi:
    ◦ Jika Persentase Kehadiran kurang dari 75.0, setiap 1% di bawah 75.0 akan mengurangi RataUtama sebanyak 0.5 poin. Misalnya, jika kehadiran 70.0 (5% di bawah 75.0), maka penalti adalah 5 * 0.5 = 2.5 poin.
    ◦ Jika Persentase Kehadiran 75.0 atau lebih, tidak ada penalti.
    ◦ Gunakan operator relasional dan aritmatika untuk kondisi ini.
• Nilai Akhir (NA):
    ◦ NA = RataUtama - Poin Penalti Absensi.
    ◦ Batasan: Nilai Akhir tidak boleh kurang dari 0 atau lebih dari 100. Jika hasil perhitungan di luar rentang ini, sesuaikan menjadi 0 atau 100 secara otomatis.
    ◦ Gunakan operator kondisional ?: untuk menerapkan batasan ini.
• Grade Huruf: Ditemukan berdasarkan NA menggunakan kriteria berikut:
    ◦ NA >= 90: 'A'
    ◦ NA >= 80: 'B'
    ◦ NA >= 70: 'C'
    ◦ NA >= 60: 'D'
    ◦ NA < 60: 'E'
    ◦ Gunakan operator kondisional ?: secara bertingkat.
• Status Kelulusan:
    ◦ "Lulus" jika Grade Huruf adalah 'A', 'B', atau 'C' DAN Persentase Kehadiran minimal 65.0.
    ◦ "Tidak Lulus" dalam kasus lainnya.
    ◦ Pengecualian Prioritas Tinggi: Jika NA kurang dari 50, terlepas dari Grade Huruf dan Persentase Kehadiran, statusnya selalu "Tidak Lulus".
    ◦ Gunakan operator logikal && atau || (secara implisit melalui operator kondisional ?:) dan operator relasional.
Output: Program harus menampilkan hasil berikut ke layar menggunakan printf(), dengan format dan presisi yang ditentukan, serta menggunakan escape sequences yang sesuai untuk tata letak:
1. NRP Mahasiswa: Ditampilkan sebagai bilangan bulat.
2. Nilai Tugas: Ditampilkan dengan dua angka di belakang koma.
3. Nilai UTS: Ditampilkan dengan dua angka di belakang koma.
4. Nilai UAS: Ditampilkan dengan dua angka di belakang koma.
5. Persentase Kehadiran: Ditampilkan dengan dua angka di belakang koma, diikuti simbol persen (%).
6. Rata-rata Nilai Utama: Ditampilkan dengan dua angka di belakang koma.
7. Nilai Akhir: Ditampilkan dengan dua angka di belakang koma.
8. Grade Huruf: Ditampilkan sebagai karakter.
9. Status Kelulusan: Ditampilkan sebagai teks ("Lulus" atau "Tidak Lulus").
Contoh Input:
502499100123456
75.0
80.0
85.0
70.0
Contoh Output:
=== Laporan Evaluasi Mahasiswa ===
NRP                  : 502499100123456
Nilai Tugas          : 75.00
Nilai UTS            : 80.00
Nilai UAS            : 85.00
Persentase Kehadiran : 70.00%
Rata-rata Utama      : 80.00
Nilai Akhir          : 77.50
Grade                : C
Status               : Lulus
