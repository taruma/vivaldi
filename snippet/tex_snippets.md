Berikut potong kode yang digunakan untuk dokumen .tex

## Untuk Laporan

Judul Laporan 

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

## Untuk Catatan

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