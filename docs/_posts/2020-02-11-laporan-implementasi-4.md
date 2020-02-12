---
permalink: laporan-implementasi-4-banding-model-variasi-RNN
---

# LI4: Perbandingan Model Variasi RNN

Judul | __Perbandingan model variasi _Recurrent  Neural Networks_ (RNN) pada kasus prediksi debit aliran.__
Tanggal Publikasi | 11 Februari 2020 (1.0.0)
Unduh | [OneDrive (PDF)](https://1drv.ms/b/s!AmxSTa4UunElhoVm7i0EuKdPkPlzVg?e=rjXNpf)
Lihat | [Google Colab](https://colab.research.google.com/drive/18U8SLe9mgCs570rVDhjypTuxK0eWPy1n), [Github Gist](https://gist.github.com/taruma/9d1ef5c6d629c792bed0c3f68b324675), [NBViewer](https://nbviewer.jupyter.org/gist/taruma/9d1ef5c6d629c792bed0c3f68b324675)
Tool | tensorflow, keras, numpy, pandas, matplotlib, hidrokit, hydroerr, seaborn 
Fokus | implementasi rnn, visualisasi data/hasil, membandingkan model
Lisensi | MIT, CC-BY-4.0

---

1. TOC
{:toc}

---

## Grafik/Plot Pada Laporan

Jika grafik pada laporan (pdf) tidak terlihat jelas, terlampir daftar grafik yang disimpan pada laporan ini.

### TAHAP 3: INPUT MODEL

#### Matriks Korelasi Dataset

![](images/li4/grafik_korelasi_matriks.png)

#### Grafik `PairPlot` Dataset

![](images/li4/grafik_pairplot_dataset.png)

### TAHAP 4: MODEL KONSEPTUAL

#### NRECA (Bulanan)

![](images/li4/grafik_hidrograf_nreca_bulanan.png)

#### NRECA (2 Periode)

![](images/li4/grafik_hidrograf_nreca_2_periode.png)

#### FJMOCK (Bulanan)

![](images/li4/grafik_hidrograf_fjmock_bulanan.png)

#### FJMOCK (2 Periode)

![](images/li4/grafik_hidrograf_fjmock_2_periode.png)

### TAHAP 6: VISUALISASI

#### Grafik $R^2$

__TRAIN SET__

![](images/li4/grafik_r2_train_set_ts5.png)
![](images/li4/grafik_r2_train_set_ts10.png)
![](images/li4/grafik_r2_train_set_ts365.png)

__TEST SET__

![](images/li4/grafik_r2_test_set_ts5.png)
![](images/li4/grafik_r2_test_set_ts5.png)
![](images/li4/grafik_r2_test_set_ts5.png)

#### Perbandingan metrik terhadap _timesteps_

$R^2$

![](images/li4/grafik_metrik_ts__r_2_.png)

$NSE$

![](images/li4/grafik_metrik_ts__nse_.png)

$MSE$

![](images/li4/grafik_metrik_ts__mse_.png)

#### `history` model

![](images/li4/grafik_history_model_loss.png)

#### Perbandingan hidrograf

Bulanan
![](images/li4/grafik_hidrograf_bulanan.png)

2 Periode
![](images/li4/grafik_hidrograf_2_periode.png)

#### Perbandingan nilai metrik antar model

$R^2$ (Bulanan)

![](images/li4/grafik_bar_banding_nilai__r_2__bulanan.png)

$NSE$ (Bulanan)

![](images/li4/grafik_bar_banding_nilai__nse__bulanan.png)

$R^2$ (2 Periode)

![](images/li4/grafik_bar_banding_nilai__r_2__2_periode.png)

$NSE$ (2 Periode)

![](images/li4/grafik_bar_banding_nilai__nse__2_periode.png)

#### Perbandingan kurva debit

__Bulanan__

Konseptual

![](images/li4/grafik_kurva_durasi_konseptual_bulanan.png)

ANN

![](images/li4/grafik_kurva_durasi_ann_bulanan.png)

RNN

![](images/li4/grafik_kurva_durasi_rnn_bulanan.png)

LSTM

![](images/li4/grafik_kurva_durasi_lstm_bulanan.png)

GRU

![](images/li4/grafik_kurva_durasi_gru_bulanan.png)

__2 Periode__

Konseptual

![](images/li4/grafik_kurva_durasi_konseptual_2_periode.png)

ANN

![](images/li4/grafik_kurva_durasi_ann_2_periode.png)

RNN

![](images/li4/grafik_kurva_durasi_rnn_2_periode.png)

LSTM

![](images/li4/grafik_kurva_durasi_lstm_2_periode.png)

GRU

![](images/li4/grafik_kurva_durasi_gru_2_periode.png)

#### Perbandingan nilai debit andal

__Bulanan__

$80\%$

![](images/li4/grafik_bar_banding_debitandal_bulanan_80.png)

$90\%$

![](images/li4/grafik_bar_banding_debitandal_bulanan_90.png)

$95\%$

![](images/li4/grafik_bar_banding_debitandal_bulanan_95.png)

__2 Periode__

$80\%$

![](images/li4/grafik_bar_banding_debitandal_2_periode_80.png)

$90\%$

![](images/li4/grafik_bar_banding_debitandal_2_periode_90.png)

$95\%$

![](images/li4/grafik_bar_banding_debitandal_2_periode_95.png)

