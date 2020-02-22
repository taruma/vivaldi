---
permalink: /daftar-makalah
---

# Daftar Makalah

{% include alert.html text="Tulisan ini merupakan catatan pribadi.<br>Dan dapat berubah-ubah."%}

Pada halaman ini tersedia daftar makalah (paper) yang saya gunakan atau kumpulkan terkait penggunaan machine learning di bidang sumberdaya air. Terdapat juga beberapa makalah yang menurut saya menarik meski tidak sesuai topik yang ingin dikaji. Daftar makalah diurutkan berdasarkan tahun publikasi. 

Halaman ini saya gunakan untuk merekam jejak bacaan yang kemungkinan saya jadikan referensi. Kemungkinan akan saya buat halaman terpisah untuk makalah/materi yang saya gunakan dalam penelitian.

-----

## Informasi Halaman
{: .no_toc}

Jenis Tulisan | Koleksi, Catatan Pribadi
Unduh | [CSV](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_paper.csv), [Excel](https://github.com/taruma/vivaldi/blob/master/docs/_data/list_paper_excel.xlsx)

-----

## Daftar Isi
{: .no_toc}

1. TOC
{:toc}


-----

## Sudah dibaca

Berikut daftar makalah yang telah saya baca (bukan berarti memahami sepenuhnya). 😁. 

print code | Tahun | Judul | Penulis | Publikasi
:-: | :-: | - | - | :-:
{%- assign collection = site.data.list_paper | sort: 'year' | reverse -%}
{%- assign read_collection = collection | where: "read", "yes" -%}
{%- for item in read_collection -%}
{% if item %}
<small>{{ item.code }}{%- if item.read == "yes" -%}<br>({%- octicon check -%},{{ item.readdate }}){%- endif -%}{%- if item.note == "yes" -%}<br>[{%- octicon book -%}]{%- endif -%}</small>|{{ item.year }}|__{{ item.title }}__{%- if item.doi -%}<br>([doi]({{ item.doi }})){%- endif -%}|{{ item.author }}|_{{ item.publisher }}_|
{%- endif -%}
{% endfor %}

Catatan:

* Yang ditandai ({%- octicon check -%}, tanggal selesai dibaca (`yyyymmdd`)) berarti sudah pernah dibaca.
* Yang ditandai [{%- octicon book -%}] berarti sudah dibuat ringkasannya.
* _Print code_ merupakan kode pribadi yang digunakan untuk menandai makalah yang telah saya cetak.

-----

## _Dropbox_

Berikut daftar makalah yang saya kumpulkan untuk dibaca. 😁. 

print code | Tahun | Judul | Penulis | Publikasi
:-: | :-: | - | - | :-:
{%- assign unread_collection = '' | split: '' -%}
{%- for item in collection -%}
{%- if item.read == nil -%}
{% if item %}
<small>{{ item.code }}{%- if item.read == "yes" -%}<br>({%- octicon check -%},{{ item.readdate }}){%- endif -%}{%- if item.note == "yes" -%}<br>[{%- octicon book -%}]{%- endif -%}</small>|{{ item.year }}|__{{ item.title }}__{%- if item.doi -%}<br>([doi]({{ item.doi }})){%- endif -%}|{{ item.author }}|_{{ item.publisher }}_|
{%- endif -%}
{%- endif -%}
{%- endfor -%}
{{ unread_collection }}