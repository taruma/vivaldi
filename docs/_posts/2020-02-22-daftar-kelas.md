---
permalink: /daftar-kelas
---

# Daftar Kelas

{% include alert.html text="Tulisan ini merupakan catatan pribadi.<br>Dan dapat berubah-ubah."%}

Halaman ini berisikan daftar kelas/kursus yang saya telah tempuh dan yang sedang diambil. 

-----

## Informasi Halaman
{: .no_toc}

Jenis Halaman | Koleksi, Catatan Pribadi
Unduh | [CSV](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_course.csv), [Excel](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_course_excel.xlsx)

-----

## Daftar Isi
{: .no_toc}
1. TOC
{: toc}

-----

## Kelas yang sedang diambil

Berikut daftar kelas yang sedang diambil. 

{% include daftar_kelas.html status="enrolled"%}

-----

## Kelas yang selesai

Berikut daftar kelas yang pernah saya ambil dan selesaikan. Setiap kelas tersedia sertifikat (atau nilai jika tidak tersedia). Kelas diurutkan dari yang terakhir diselesaikan (yang paling atas, yang baru saja selesai). 

{% include daftar_kelas.html %}

-----


## Kelas yang akan diambil

Berikut daftar kelas yang akan diambil. 

{% include daftar_kelas.html status="next"%}
