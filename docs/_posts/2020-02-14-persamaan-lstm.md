---
permalink: persamaan-lstm
---

# Persamaan LSTM

{% include alert.html text="Tulisan ini merupakan catatan pribadi.<br>Dan dapat berubah-ubah." %}

Tulisan dibawah ini merupakan ringkasan (dan catatan tambahan pribadi) dari makalah berjudul "_Rainfall-runoff modelling using Long Short-Term Memory (LSTM) networks_" oleh Kratzert, dkk (2018)[^1]. 

---

## Informasi Tulisan
{: .no_toc}

Jenis Tulisan | Catatan Pribadi
Unduh (Tulisan Tangan) | [OneDrive (PDF)](https://1drv.ms/b/s!AmxSTa4UunElhoYjjYF_OAum4VVy9w?e=pUm9d6)
Ilustrasi | Berdasarkan [^1]

---

## DAFTAR ISI
{: .no_toc}

1. TOC
{:toc}

---

![Contoh Umum RNN dua layer](images/eq_lstm/00_general.png "Contoh Umum RNN Dua Layer (gambar ulang dari makalah)")

## _Recurrent Neural Networks_ (RNN)

![](images/eq_lstm/01_rnn.png "Sel Recurrent Neural Networks")

Pada sel RNN, hanya terdapat satu _internal state_ $h_t$.

$$\boldsymbol{h}_t = g(\mathbf{W}\boldsymbol{x}_t + \mathbf{U} \boldsymbol{h}_{t-1} + \boldsymbol{b})$$

dengan: 
- $g(\cdot)$ sebagai _activation function_, yang digunakan biasanya $\tanh(\cdot)$.
- $\mathbf{W}$ dan $\mathbf{U}$ merupakan matriks bobot dari _hidden state_ dan input $\boldsymbol{x}$.
- $\boldsymbol{b}$ merupakan bias.

catatan:
- $\mathbf{W}, \mathbf{U}, \boldsymbol{b}$ dapat disesuaikan (_adjustable_).
- $\boldsymbol{h}_t$ diinisiasi dengan nilai $\vec{0}$.

---

## _Long Short-Term Memory_ (LSTM)

![](images/eq_lstm/02_lstm.png "Sel Long Short-Term Memory")

Sebagai perbandingan, LSTM memiliki:
1. _cell state_ tambahan atau sel memori $\boldsymbol{c}_t$.
2. _gate_ yang mengatur alur informasi pada sel LSTM.

## LSTM GATE
{: .no_toc}

### _Forget Gate_ ($\boldsymbol{f}$)

_Forget gate_ $\boldsymbol{f}$, mengatur elemen dari vektor _cell state_ $\boldsymbol{c}_{t-1}$ yang akan dilupakan:

$$\boldsymbol{f}_t = \sigma(\mathbf{W}_f\boldsymbol{x}_t+\mathbf{U}_f\boldsymbol{h}_{t-1}+\boldsymbol{b}_f)$$

dengan:

- $\sigma(\cdot)$ merupakan persamaan logistik sigmoid.
- $\mathbf{W}\_f, \mathbf{U}\_f, \boldsymbol{b}\_f$ merupakan set parameter yang dapat dilatih di _forget gate_.

### _Potential Update Vector_ ($\widetilde{\boldsymbol{c}}_t$)

Selanjutnya, _potential update vector_ untuk _cell state_ $\widetilde{\boldsymbol{c}}_t$.

$$\widetilde{\boldsymbol{c}}_t=\tanh(\mathbf{W}_{\widetilde{c}}\boldsymbol{x}_t+\mathbf{U}_{\widetilde{c}}\boldsymbol{h}_{t-1}+\boldsymbol{b}_{\widetilde{c}})$$

dengan:

- $\widetilde{\boldsymbol{c}}_t$ vektor bernilai rentang $(-1, 1)$.
- $\tanh(\cdot)$ merupakan fungsi hiperbolik tangen.
- $\mathbf{W}\_{\widetilde{c}}, \mathbf{U}\_{\widetilde{c}}, \boldsymbol{b}\_{\widetilde{c}}$ merupakan _learnable parameters_.

### _Input Gate_ ($\boldsymbol{i}$)

*Input gate* menentukan informasi dari $\widetilde{\boldsymbol{c}}_t$ yang digunakan untuk memperbarui *cell state* pada *current timestep*.

$$\boldsymbol{i}_t=\sigma({\mathbf{W}_i\boldsymbol{x}_t+\mathbf{U}_i\boldsymbol{h}_{t-1}+\boldsymbol{b}_i})$$

dengan:

- $\boldsymbol{i}_t$, vektor bernilai antara $(0, 1)$.
- $\mathbf{W}_i, \mathbf{U}_i, \boldsymbol{b}_i$: *learnable parameters*.

### _Cell State_ ($\boldsymbol{c}_t$)

Nilai *cell state* diperbarui dengan:

$$\boldsymbol{c}_t=\boldsymbol{f}_t\odot\boldsymbol{c}_{t-1}+\boldsymbol{i}_t\odot\widetilde{\boldsymbol{c}}_t$$

dengan:

- $\boldsymbol{f}\_t, \boldsymbol{i}\_t$ bernilai pada rentang $(0, 1)$. Variabel tersebut menentukan nilai pada $\boldsymbol{c}\_{t-1}, \widetilde{\boldsymbol{c}}\_t$ yang perlu diingat $(\boldsymbol{f}\_t \approx \vec{1}, \boldsymbol{i}\_t\approx\vec{1})$ atau dilupakan $(\boldsymbol{f}\_t\approx\vec{0}, \boldsymbol{i}\_t\approx\vec{0})$

catatan:

- seperti _hidden state_, _cell state_ diinisiasi dengan nilai $\vec{0}$.

### _Output Gate_ ($\boldsymbol{o}$)

*Output gate* $\boldsymbol{o}$ mengatur informasi dari $\boldsymbol{c}_t$ yang masuk ke *hidden state* $\boldsymbol{h}_t$.

$$
\boldsymbol{o}_t=\sigma(\mathbf{W}_o\boldsymbol{x}_t+\mathbf{U}_o\boldsymbol{h}_{t-1}+\boldsymbol{b}_o)
$$

dengan:

- $\boldsymbol{o}_t$, vektor bernilai antara $(0, 1)$.
- $\mathbf{W}\_o, \mathbf{U}\_o, \boldsymbol{b}\_o$ merupakan _learnable parameters_.

### _Hidden state_ (LSTM) ($\boldsymbol{h}_t$)

dari $\boldsymbol{o}_t$, diperoleh nilai baru $\boldsymbol{h}_t$:

$$
\boldsymbol{h}_t=\tanh(\boldsymbol{c}_t)\cdot\boldsymbol{o}_t
$$

### _Final/Output layer_ ($y$)

pada layer terakhir, nilai hasil sel dihubungkan dengan jaringan/neuron dengan keluaran tunggal.

$$
y=\mathbf{W}_d\boldsymbol{h}_n+\boldsymbol{b}_d
$$

dengan:

- $y$: nilai debit/limpasan.
- $\boldsymbol{h}_n$: hasil dari sel terakhir.
- $\mathbf{W}_d$ sebagai bobot neuron dan $\boldsymbol{b}_d$ sebagai bias.

## Ringkasan Persamaan

![](images/eq_lstm/03_lstm_detail.png "Persamaan LSTM (Detail)")

No | Persamaan | Fungsi
:- | :-: | :-
1 | $$\boldsymbol{h}_t = g(\mathbf{W}\boldsymbol{x}_t + \mathbf{U} \boldsymbol{h}_{t-1} + \boldsymbol{b})$$ | *hidden state* (RNN)
2 | $$\boldsymbol{f}_t = \sigma(\mathbf{W}_f\boldsymbol{x}_t+\mathbf{U}_f\boldsymbol{h}_{t-1}+\boldsymbol{b}_f)$$ | _forget gate_
3 | $$\widetilde{\boldsymbol{c}}_t=\tanh(\mathbf{W}_{\widetilde{c}}\boldsymbol{x}_t+\mathbf{U}_{\widetilde{c}}\boldsymbol{h}_{t-1}+\boldsymbol{b}_{\widetilde{c}})$$ | _potential vector update_
4 | $$\boldsymbol{i}_t=\sigma({\mathbf{W}_i\boldsymbol{x}_t+\mathbf{U}_i\boldsymbol{h}_{t-1}+\boldsymbol{b}_i})$$ | _input gate_
5 | $$\boldsymbol{c}_t=\boldsymbol{f}_t\odot\boldsymbol{c}_{t-1}+\boldsymbol{i}_t\odot\widetilde{\boldsymbol{c}}_t$$ | _cell state_
6 | $$\boldsymbol{o}_t=\sigma(\mathbf{W}_o\boldsymbol{x}_t+\mathbf{U}_o\boldsymbol{h}_{t-1}+\boldsymbol{b}_o)$$ | _output gate_
7 | $$\boldsymbol{h}_t=\tanh(\boldsymbol{c}_t)\cdot\boldsymbol{o}_t$$ | _hidden state_ (LSTM)
8 | $$y=\mathbf{W}_d\boldsymbol{h}_n+\boldsymbol{b}_d$$| _final/dense layer_

---

Catatan:

- $$\mathbf{x} = \left[\boldsymbol{x}_1, \boldsymbol{x}_2, \cdots, \boldsymbol{x}_n \right]$$, merupakan masukan observasi meteorologi dengan _complete sequence_. Dengan $n$ merupakan jumlah _timestep_ yang digunakan.
  - Untuk setiap langkah (_timesteps_), $\boldsymbol{x}_t$ merupakan vektor berisikan informasi meteorologi pada langkah $t$. 
- Pada kasus lapisan LSTM berganda (_multiple-stacked_ LSTM), lapisan berikutnya menerima hasil dari layer sebelumnya, $\mathbf{h}=[\boldsymbol{h}_1, \boldsymbol{h}_2, \cdots, \boldsymbol{h}_n]$.
- Nilai akhir dihitung menggunakan keluaran $\boldsymbol{h}_n$.

--- 

[^1]: Kratzert, F., Klotz, D., Brenner, C., Schulz, K., Herrnegger, M., 2018. Rainfall–runoff modelling using Long Short-Term Memory (LSTM) networks. Hydrology and Earth System Sciences 22, 6005–6022. https://doi.org/10.5194/hess-22-6005-2018

