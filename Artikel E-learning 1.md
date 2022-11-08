# **Notebooks vs Python Projects**
Halo *guys*, dalam mengembangkan *project* atau *project development* perangkat lunak sering kali menggunakan berbagai bahasa pemrograman. Salah satunya adalah bahasa pemrograman python. Tapi tau ga sih, kita kadang belum bisa membedakan antara *notebooks* dan python *projects*. 

*So, let me tell you about the difference.*

Pada python *projects* yang reguler menggunakan format .py yaitu sebuah *plain text* yang hanya mengandung kode pemrograman python saja, sedangkan *notebooks* menggunakan format .ipynb. Adapun kelebihan dan kekurangan antara python *projects* dan *notebooks*, berikut ini komparasi dari kelebihannya.

| *Phyton Projects*                                   | *Notebooks*                                                                    |
|-----------------------------------------------------|--------------------------------------------------------------------------------|
| Sangat sederhana dan mendasar                       | Terdapat representasi media dan pemformatan teks                               |
| *Runs* tanpa server atau browser apa pun            | Sudah termasuk instalasi Anaconda                                              |
| Hanya membutuhkan instalasi Anaconda                | Memiliki kemampuan matematika, seperti membuat bagan, grafik, dsb              |
| Memiliki debugger bawaan                            | *Notebook* yang dibuat di Jupyter dapat diakses/edit menggunakan web *browser* |
| Dapat disesuaikan sesuai dengan preferensi pengguna | Sudah termasuk *debugger*                                                      |
| Secara otomatis menyimpan perubahan membuat kode    |                                                                                |

Adapun komparasi dari kekurangan *python projects* dan *notebook,* sebagai berikut.

| *Phyton Projects*                                                                         | *Notebooks*                                                                                                                                   |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| File tidak dapat diakses langsung dengan perangkat lain, kecuali disalin / dikirim        | Tidak dapat bekerja secara offline, sehingga memerlukan server dan web *browser*                                                              |
| Perubahan tidak disimpan secara otomatis saat membuat kode                                | Instalasinya membutuhkan waktu lebih lama daripada IDE lain                                                                                   |
| Tidak disarankan untuk mengembangkan program yang kompleks dan menggunakan banyak library | Mengaksesnya dengan localhost secara *default*, sehingga harus mengikuti langkah keamanan yang signifikan untuk mengaksesnya dari server lain |

## **Instalasi *Jupyter Notebooks***
Notebooks merupakan suatu software buatan Jupyter. Aplikasi yang paling umum digunakan dalam mengembangkan Jupyter *Notebooks* adalah JupyterLab. Terdapat dua cara umum dalam pengerjaannya, yaitu a) secara lokal menggunakan komputer, dan b) berbasis *cloud.*

### 1) **Secara Lokal Menggunakan Komputer**

Rekomendasi untuk instruksi resmi untuk *install* JupyterLab yaitu <https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html>.

Kami lebih memilih untuk instalasi JupyterLab melalui conda:

```
conda install -c conda-forge jupyterlab
```

Setelah berhasil instalasi, selanjutnya dapat mengetik jupyter lab di dalam terminal Anaconda Prompt dan tekan *Enter* di *keyboard*, dan JupyterLab akan terbuka secara otomatis di dalam web *browser.*

![1](https://user-images.githubusercontent.com/37721749/200547097-6da58264-6cd2-417f-9a22-975440ab658b.png)

### 2) **Berbasis *Cloud***

Jika lebih memilih mengerjakannya berbasis *cloud*, cara mudah dan gratis adalah menggunakan Google *Colab.* Kamu dapat mengakses nya melalui pranala *<https://colab.research.google.com/>*. 

Jika lebih suka mengerjakannya dengan *hardware* pribadi, kami merekomendasikan menggunakan *platform [Grid.ai](https://www.grid.ai/)*. Langkah awalnya kamu harus membuat *session* di Grid.ai*  melalui web *browser*, setelahnya kamu dapat membuka JupyterLab *directory.*

## **Persiapan *Basic Python* *Projects***
*Python Project* dasar dapat dimulai dengan struktur folder sederhana. Struktur yang tepat tergantung pada konteks kasus penggunaan, tetapi paling sering dimulai dengan dua folder yaitu:

>1. src untuk file kode (.py scripts)
>2. docs  untuk file yang terkait dengan dokumentasi

File `README.md` juga sering kali merupakan file untuk menggantikan instruksi umum.

#### **Mengubah *Project* menjadi *Python Package***
Misalkan kita memiliki file mycode.py yang berisi kode. Kode tersebut dapat diubah menjadi *Python package* sehingga fungsi dari kode tersebut dapat diimpor. Untuk melakukan ini, kami membuat folder bernama mypackage (dan pilihan penamaan arbitrer) yang berisi setidaknya 2 hal ini:

>1. File bernama `\_\_init\_\_.py` (bisa kosong)
>2. Sebuah file yang berisi kode kita yang bernama `mycode.py` (nama arbiter lain)

Terakhir, kami membuat file `setup.py`

```
import setuptools

setuptools.setup(
name='mypackage',
version='0.1',
author='Himpasikom',
packages=setuptools.find\_packages(),
)
```

File `setup.py` ini harus berada di sebelah folder mypackage. Setelah membuat file-file ini, file tersebut akan terlihat seperti berikut:

![2](https://user-images.githubusercontent.com/37721749/200547204-e3b9dc2e-1670-4915-ad73-76d965be0425.png)

Sekarang, kita dapat menginstal paket menggunakan perintah:

```
pip install -e path/to/the/folder/containing/setup.py
```

![3](https://user-images.githubusercontent.com/37721749/200547686-5191aa0e-1f2b-4621-9242-138481ba54e0.png)

Terakhir, setelah menyelesaikan langkah ini, kita dapat *import* kode dari package dengan Python, di mana saja di komputer kita.

![4](https://user-images.githubusercontent.com/37721749/200547720-f8b4a997-699b-4ffb-90c7-4a4158b83695.png)
