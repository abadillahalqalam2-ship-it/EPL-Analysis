# EPL-Analysis
Excel dashboard and SQL analysis of 9,380 Premier League matches (2000/01-2024/25) comparing home vs away performance: win rate, shot conversion, and discipline.

# Analisis Performa Kandang vs Tandang Premier League (2000/01 - 2024/25)

![Dashboard EPL](https://github.com/abadillahalqalam2-ship-it/EPL-Analysis/blob/main/Dashboard%20Excel.PNG))

Analisis deskriptif 9.380 pertandingan Premier League selama 25 musim untuk memahami mengapa performa tandang jauh tertinggal dari kandang, dan faktor taktis apa yang membedakannya. Dashboard dibuat dengan Microsoft Excel (PivotTable dan slicer), lalu diverifikasi ulang dengan SQL dan Python.

## Business Problem

Win rate tim tandang jauh di bawah tim kandang, disertai pelanggaran dan kartu yang lebih banyak. Stakeholder (simulasi): Manajer Tim / Head of Sports Analytics, yang membutuhkan dasar data untuk penyesuaian taktik laga tandang.

## Dataset

- Sumber: Premier League Match Details 25 Seasons (Kaggle) (https://github.com/abadillahalqalam2-ship-it/EPL-Analysis/blob/main/Dataset_EPL.xlsx)
- 9.380 pertandingan, musim 2000/01 sampai 2024/25 (pertandingan terakhir 5 Mei 2025)
- Tidak ada missing value pada data pertandingan
- Skema bintang: satu tabel fakta (`TableFakta`) dan enam tabel dimensi (Season, MatchDate, HomeTeam, AwayTeam, FullTime, HalfTime)

## KPI dan Hasil

| KPI | Kandang | Tandang |
|---|---|---|
| Win rate | 45,83% | 29,51% |
| Gol per laga | 1,54 | 1,18 |
| Shots per laga | 13,62 | 10,81 |
| Shots on target per laga | 5,97 | 4,69 |
| Conversion (gol / shots on target) | 25,71% | 25,20% |
| Fouls (total) | 105.772 | 110.362 |
| Kartu kuning (total) | 13.771 | 16.813 |
| Kartu merah (total) | 586 | 800 |

Hasil seri: 24,66% dari seluruh pertandingan.

Catatan: grafik "Tim Indisipliner" pada dashboard hanya menampilkan kartu saat tim bermain kandang. Perbandingan kandang vs tandang ada pada tabel di atas.

## Insight

1. **Keunggulan kandang nyata.** Selisih win rate sekitar 16 poin persentase.
2. **Masalah tandang ada pada volume peluang, bukan finishing.** Conversion hampir sama (25,7% vs 25,2%), tetapi tim tandang menghasilkan sekitar 2,8 shots lebih sedikit per laga.
3. **Tekanan lawan berkaitan dengan hasil.** Saat tuan rumah menang, rata-rata shots mereka 14,8. Saat tamu menang, 12,0.
4. **Tim tandang kurang disiplin.** Fouls sekitar 4% lebih banyak, kartu kuning sekitar 22% lebih banyak, kartu merah sekitar 37% lebih banyak.

## Rekomendasi

- Pendekatan tandang yang lebih kompak dengan transisi serangan balik cepat untuk menaikkan volume tembakan.
- Latihan antisipasi set-piece, karena tuan rumah rata-rata mendapat 6,04 corner dibanding 4,77 untuk tamu.
- Pemantauan kartu dari pelanggaran non-taktis.

## Keterbatasan

- Analisis bersifat **deskriptif, bukan kausal**. Hubungan antara shots dan hasil laga tidak membuktikan sebab-akibat.
- Angka di atas adalah rata-rata seluruh liga. Untuk analisis satu klub, filter per `HomeTeam` / `AwayTeam`.
- Perbedaan kartu bisa dipengaruhi kualitas lawan (confounding) yang belum dikontrol.
- Data hanya mencakup statistik akhir pertandingan. Penguasaan bola, jarak tempuh pemain, dan akurasi umpan tidak tersedia.
- Dugaan penurunan performa pada Desember-Januari tidak terlihat di data ini (win rate bulanan relatif stabil).


## Tools

Microsoft Excel (PivotTable, slicer, XLOOKUP), SQL
