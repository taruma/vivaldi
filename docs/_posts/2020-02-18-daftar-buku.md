---
permalink: /daftar-buku
---

# Daftar Buku

{% include alert.html text="Tulisan ini merupakan catatan pribadi.<br>Dan dapat berubah-ubah."%}

Halaman ini berisikan daftar buku yang saya kumpulkan dan gunakan. 

-----

## Informasi Halaman
{: .no_toc}

Jenis Halaman | Koleksi, Catatan Pribadi
Unduh | [CSV](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_book.csv), [Excel](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_book_excel.xlsx)

-----

## Daftar Isi
{: .no_toc}

1. TOC
{:toc}


-----

## Yang Digunakan

Berikut daftar buku yang saya gunakan sebagai referensi.

Judul | Penulis | Penerbit | Catatan
:- | :- | :-: | :- |
{%- assign collection = site.data.list_book -%}
{%- assign read_collection = collection | where: "use", "yes" | sort: 'year' | reverse -%}
{%- for item in read_collection -%}
{% if item %}
___{{ item.title }}___ ({{ item.year | date: "%Y"}}){%- if item.isbn -%}<br><sup>isbn: {{ item.isbn }}</sup>{%- endif -%} | _{{ item.author }}_ | __{{ item.publisher }}__ | <sup>{{ item.note }}</sup>
{%- endif -%}
{% endfor %}

-----

## _Dropbox_

Berikut daftar buku yang saya kumpulkan saat melakukan pencarian. 

Judul | Penulis | Penerbit |
:- | :- | :-: |
{%- assign collection = site.data.list_book | sort: 'year' | reverse -%}
{%- for item in collection -%}
{% if item.use == nil %}
___{{ item.title }}___ ({{ item.year | date: "%Y"}}){%- if item.isbn -%}<br><sup>isbn: {{ item.isbn }}</sup>{%- endif -%} | _{{ item.author }}_ | __{{ item.publisher }}__ | 
{%- endif -%}
{% endfor %}