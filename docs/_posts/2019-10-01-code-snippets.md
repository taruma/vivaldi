---
permalink: /code-snippets
---

# Code Snippets

1. TOC
{:toc}

---

## LaTeX Snippets

### Judul Laporan 

```tex
    % MY EDIT
	% ref: https://tex.stackexchange.com/questions/131015/page-break-after-every-section
	\let\oldsection\section
	\renewcommand\section{\clearpage\oldsection} 

    % Document title
    \title{Prediksi Debit Aliran Menggunakan \emph{Long Short-Term Memory} (LSTM)}
    \author{Taruma Sakti Megariansyah}
    \date{22 Oktober 2019}

\begin{document}
   
%    \maketitle
%	ref: https://stackoverflow.com/questions/3141702/vertically-centering-a-title-page
	\begin{titlepage}
		\vspace*{\fill}
		\begin{center}
 		\normalsize Laporan Implementasi \\
		\huge Prediksi Debit Aliran menggunakan \emph{Long Short-Term Memory} (LSTM)\\ 
		\normalsize Versi 1.0.0 \\[0.2cm]
      	\small Berdasarkan \emph{Jupyter Notebook}: \texttt{github-taruma\_demo\_lstm\_rr.ipynb} \\[0.5cm]
		\normalsize oleh Taruma Sakti Megariansyah\\[0.5cm]
      	\normalsize 22 Oktober 2019\\[1cm]
    	\adjustimage{max size={0.9\linewidth}{1cm}}{github_taruma_demo_lstm_rr_files/vivaldi_logo.png}\\
      	\normalsize github.com/taruma/vivaldi
		\end{center}
    	\vspace*{\fill}
	\end{titlepage}
```

### Laporan Implementasi (hidrokit+vivaldi)

```tex
    % MY EDIT
	% ref: https://tex.stackexchange.com/questions/131015/page-break-after-every-section
	\let\oldsection\section
	\renewcommand\section{\clearpage\oldsection} 

\begin{document}
   
%    \maketitle
%	ref: https://stackoverflow.com/questions/3141702/vertically-centering-a-title-page
	\begin{titlepage}
		\vspace*{\fill}
		\begin{center}
 		\normalsize Laporan Implementasi \\
		\huge Prediksi Kualitas Air menggunakan \emph{Artificial Neural Networks} (ANN)\\ 
		\normalsize Versi 2.0.0 \\[0.2cm]
      	\small Berdasarkan \emph{Jupyter Notebook}: \texttt{taruma\_demo\_ann\_ka\_2\_0\_0.ipynb} \\[0.5cm]
      	\normalsize Buku ini menyajikan implementasi \emph{Deep Learning} pada kasus memprediksikan kualitas air. \\[0.5cm]
		\normalsize oleh Taruma Sakti Megariansyah\\[0.5cm]
      	\normalsize 13 Juli 2019\\[1cm]
    	\adjustimage{max size={0.9\linewidth}{1cm}}{hidrokit_logo.jpg}\\
      	\normalsize github.com/taruma/hidrokit \\[0.5cm]
      	\adjustimage{max size={0.9\linewidth}{1cm}}{vivaldi_logo.png}\\
      	\normalsize github.com/taruma/vivaldi
		\end{center}
    	\vspace*{\fill}
	\end{titlepage}
```

### Catatan

Judul Catatan

```tex
    % Document title
    \title{Prediksi Debit Aliran Menggunakan \emph{Long Short-Term Memory} (LSTM)}
    \author{Taruma Sakti Megariansyah}
    \date{22 Oktober 2019}

\begin{document}
  
%    \maketitle
%	ref: https://stackoverflow.com/questions/3141702/vertically-centering-a-title-page
	\begin{titlepage}
		\vspace*{\fill}
		\begin{center}
 		\normalsize Catatan Laporan\\
		\huge Prediksi Debit Aliran menggunakan \emph{Long Short-Term Memory} (LSTM)\\ 
		\normalsize Versi 1.0.0 \\[0.2cm]
      	\small Berdasarkan \emph{Jupyter Notebook}: \texttt{github-taruma\_demo\_lstm\_rr\_catatan.ipynb} \\[0.5cm]
		\normalsize oleh Taruma Sakti Megariansyah\\[0.5cm]
      	\normalsize 22 Oktober 2019\\[1cm]
    	\adjustimage{max size={0.9\linewidth}{1cm}}{vivaldi_logo.png}\\
      	\normalsize github.com/taruma/vivaldi
		\end{center}
    	\vspace*{\fill}
	\end{titlepage}
```

### `hidrokit` contrib

```tex
\begin{document}
  
%    \maketitle
%	ref: https://stackoverflow.com/questions/3141702/
	\begin{titlepage}
		\vspace*{\fill}
		\begin{center}
 		\normalsize Manual / Referensi Modul \texttt{hidrokit.contrib.taruma}\\
		\huge \texttt{.hkXX}: _\\ 
		\small telah tersedia pada versi hidrokit 0.3._ \\[0.2cm]
      	\small Berdasarkan \emph{Jupyter Notebook}: \texttt{github-taruma\_hk.ipynb} \\[0.5cm]
      	\small __ \\[0.5cm]
		\normalsize oleh Taruma Sakti Megariansyah\\[0.5cm]
      	\normalsize 26 September 2019 (1.0.0)\\[1cm]
    	\adjustimage{max size={0.9\linewidth}{1cm}}{hidrokit_logo.jpg}\\
      	\normalsize github.com/taruma/hidrokit
		\end{center}
    	\vspace*{\fill}
	\end{titlepage}
```