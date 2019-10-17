# Info Dataset

Dokumen ini menjelaskan dataset yang digunakan dalam buku.

## Dataset

Dataset merupakan data hidrologi dan klimatologi __harian__ dari tanggal __1 Maret 1998__ sampai __31 Desember 2008__ (3959 hari). Dataset terpisah menjadi 3 kategori yaitu: data curah hujan, data klimatologi, dan data debit.

- Data curah hujan diperoleh dari 8 stasiun yaitu: `bojong_manik`, `gunung_tunggal`, `pasir_ona`, `sampang_peundeuy`, `cimarga`, `bd_pamarayan`, `ciminyak_cilaki`, `gardu_tanjak`.
- Data debit diperoleh dari 1 stasiun yaitu: `bd_pamarayan`.
- Data klimatologi diperoleh dari 1 stasiun yaitu: `geofisika_serang`.

### Ringkasan Dataset

- Seluruh dataset merupakan data __harian__ dimulai dari tanggal __1 Januari 1998__ sampai __31 Desember 2008__ (4018 hari), kecuali data debit yang dimulai dari tanggal __1 Maret 1998__.
- Periode dataset dalam pemodelan dimulai dari tanggal __3 Maret 1998__ hingga __31 Desember 2008__.
- Data curah hujan memiliki 8 stasiun, data debit memiliki 1 stasiun, dan data klimatologi memiliki 1 stasiun. 
- Data curah hujan merupakan data berkolom tunggal yang menunjukkan besarnya curah hujan dalam satuan $mm$ untuk masing-masing stasiun.
- Data debit merupakan data berkolom tunggal yang menunjukkan besarnya debit dalam satuan $m^3/s$.
- Data klimatologi merupakan data dengan 10 kolom berupa:
  - Arah angin saat kecepatan maksimum (ddd_x) dalam satuan derajat
  - Arah angin terbanyak (ddd_car) dalam satuan derajat
  - Curah hujan (RR) dalam satuan $mm$
  - Kecepatan angin maksimum (ff_x) dalam satuan $m/s$
  - Kecepatan angin rata-rata (ff_avg) dalam satuan $m/s$
  - Kelembapan rata-rata (RH_avg) dalam satuan %
  - Lamanya penyinaran matahari (ss) dalam satuan jam
  - Temperatur maksimum (Tx) dalam derajat Celcius
  - Temperatur minimum (Tn) dalam derajat Celcius
  - Temperatur rata-rata (Tavg) dalam derajat Celcius
- Data debit merupakan variabel dependen, sedangkan data lainnya merupakan variabel independen.