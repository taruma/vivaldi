---
permalink: /daftar-kelas
hide: true
---

# Daftar Kelas

{% include alert.html text="Tulisan ini merupakan catatan pribadi.<br>Dan dapat berubah-ubah."%}

Halaman ini berisikan daftar kelas/kursus yang saya telah tempuh dan yang sedang diambil. 

-----

## Informasi Tulisan
{: .no_toc}

Jenis Halaman | Koleksi, Catatan Pribadi
Unduh | [CSV](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_course.csv), [Excel](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_course_excel.xlsx)

-----

## Daftar Isi
{: .no_toc}
1. TOC
{: toc}

-----

{% include daftar_kelas.html legend="yes" %}

-----

## Kelas yang sedang diambil

Berikut daftar kelas yang sedang diambil. 

{% include daftar_kelas.html status="enrolled"%}

-----

## Kelas yang selesai

Berikut daftar kelas yang pernah saya ambil dan selesaikan. 

{% include daftar_kelas.html %}

-----



## Kelas yang akan diambil

Berikut daftar kelas yang akan diambil. 

{% include daftar_kelas.html status="next"%}
